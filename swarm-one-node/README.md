# 1. Create swarm cluster
```bash
docker swarm init --advertise-addr 192.168.56.10
docker swarm join-token -q manager
docker swarm join-token -q worker
docker swarm join --token 192.168.56.10:2376
```
# 2. Use vagrant docker vm 
```bash
docker context create docker-swarm --default-stack-orchestrator=swarm --docker host=tcp://192.168.56.10:2376
docker context use docker-swarm
```