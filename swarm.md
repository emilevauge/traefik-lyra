docker-machine create --driver virtualbox mh-keystore
    
# consul
eval (docker-machine env mh-keystore)
docker run -d \
    -p "8500:8500" \
    -h "consul" \
    progrium/consul -server -bootstrap
    
docker-machine create --driver virtualbox \
    --swarm --swarm-master \
    --swarm-discovery="consul://(docker-machine ip mh-keystore):8500" \
    --engine-opt="cluster-store=consul://(docker-machine ip mh-keystore):8500" \
    --engine-opt="cluster-advertise=eth1:2376" \
    mhs-demo0
    
docker-machine create --driver virtualbox \
    --swarm \
    --swarm-discovery="consul://(docker-machine ip mh-keystore):8500" \
    --engine-opt="cluster-store=consul://(docker-machine ip mh-keystore):8500" \
    --engine-opt="cluster-advertise=eth1:2376" \
    mhs-demo1

    
# network
eval (docker-machine env --swarm mhs-demo0)
docker network create --driver overlay --subnet=10.0.9.0/24 my-net

# traefik
docker (docker-machine config mhs-demo0) run \
    -d \
    -p 80:80 -p 8080:8080 \
    --net=my-net \
    -v /var/lib/boot2docker/:/ssl \
    containous/traefik \
    -l DEBUG \
    -c /dev/null \
    --docker \
    --docker.domain traefik \
    --docker.endpoint tcp://(docker-machine ip mhs-demo0):3376 \
    --docker.tls \
    --docker.tls.ca /ssl/ca.pem \
    --docker.tls.cert /ssl/server.pem \
    --docker.tls.key /ssl/server-key.pem \
    --docker.tls.insecureSkipVerify \
    --docker.watch  \
    --web
    
    
# deploy apps
eval (docker-machine env --swarm mhs-demo0)
docker run -d --name=whoami0 --net=my-net --env="constraint:node==mhs-demo0" emilevauge/whoami
docker run -d --name=whoami1 --net=my-net --env="constraint:node==mhs-demo1" emilevauge/whoami

# test it
curl -H Host:whoami0.traefik http://(docker-machine ip mhs-demo0)
    
    
curl -X POST http://localhost:8080/v2/apps -d @examples/whoami.json -H "Content-type: application/json"
