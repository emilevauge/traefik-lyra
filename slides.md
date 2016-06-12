% title: Træfɪk 
% subtitle: Microservices vs. reverse-proxy
% author: Emile Vauge
% author: Lyra 2016
% thankyou: Thank you!
% contact: <a href="https://traefik.io">traefik.io</a>
% contact: <a href="https://containo.us">containo.us</a>
% contact: <a href="https://twitter.com/traefikproxy">@traefikproxy</a>
% contact: <a href="https://twitter.com/emilevauge">@emilevauge</a>
% favicon: figures/traefik.icon.png

---
title: /WhoamI

- DevOps, Developer
- I ❤ Docker 🐳, I ❤ Go
- I have been working @ Thales, Airbus, Lyra, Zenika
- Creator and maintainer of træfik <img src=figures/traefik.icon.png />

---
title: Why another reverse-proxy ?
class: img-top-center

<img height=400 src=figures/why.jpg />

---
title: Microservices
class: img-top-center

<img src=figures/microservices.jpg />

---
title: Containers
class: img-top-center

<img height=150 src=figures/docker-logo.png />

<img height=130 src=figures/rkt.png />


---
title: Real containers vs. Docker
class: img-top-center

<img height=450 src=figures/containers.jpg />


---
title: VM vs. Containers
class: img-top-center

<img height=450 src=figures/what-is-vm-docker-diagram.png />


---
title: Docker & Linux kernel
class: img-top-center

<img height=450 src=figures/DockerKernel.png />

---
title: Copy on write
class: img-top-center

<img height=450 src=figures/copyOnWrite.png />

---
title: Orchestration
class: img-top-center

<img height=200 src=figures/mesos-logo.jpeg />
<img height=200 src=figures/swarm.png />

---
title: Service discovery
class: img-top-center

<img height=200 src=figures/consul-logo.png />

<img height=150 src=figures/etcd-logo.png />

---
title: Reverse-proxy
class: img-top-center

<img height=500 src=figures/traditionnalArchitecture.png />

---
title: *.conf
class: img-top-center

<img height=500 src=figures/traditionnalArchitecture.config.png />


---
class: img-top-center

<img height=500 src=figures/complexity.gif />

---
title: Here comes
class: img-top-center

<img height=400 src=figures/traefik.logo.svg />

---
title: Træfik
class: img-top-center

<img height=500 src=figures/traefikArchitecture.png />

---
title: Features
build_lists: true


- **Single binary** Did I say I ❤ Go ?
- **Backends**: Docker, Swarm, Mesos / Marathon, Consul, Etcd, Zookeeper...
- **Hot reloading**
- **Load-balancing**: WRR, DRR
- **Circuit breakers**
- **Replay**
- **HTTP2**

---
title: Demo
class: img-top-center

<img height=400 src=figures/priere.jpg />

---
title: Great!
subtitle: But wait, how do you manage SSL certs?
class: img-top-center

<img height=400 src=figures/greatBut.gif />

---
title: Let's Encrypt
subtitle: Free, automated certificate authority
class: img-top-center

<img height=200 src=figures/letsencrypt-logo-horizontal.svg />


---
title: Docker official image
subtitle: docker pull traefik
class: img-top-center

<img height=400 src=figures/docker.image.png />


---
title: One for the road
subtitle: And now, Kubernetes Ingress support!
class: img-top-center

<br/>
<img height=200 src=figures/k8s.logo.svg />
---
class: img-top-center

<br/>
<br/>
<br/>

<img height=150 src=https://img.shields.io/github/stars/containous/traefik.svg?style=social&label=Star />

---
title: Now part of
class: img-top-center

- Cisco Cloud
<img height=150 src=figures/mantl-logo.png />

- Cap Gemini
<img height=150 src=figures/apollo-logo.png />

---
title: Then I created a startup
class: img-top-center

<img height=130 src=figures/zenika.logo.png />

<img height=150 src=figures/arrow.jpg />

<img height=150 src=figures/containous.logo.png />



---
title: June 2016
class: img-top-center

<img height=400 src=figures/kelseyhightower.1.png />


---
title: 30 minutes later...
class: img-top-center

<img height=400 src=figures/kelseyhightower.2.png />

