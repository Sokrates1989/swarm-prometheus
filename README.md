# swarm-prometheus
Swarm deployment for the monitoring tool prometheus

# Preparations

.env
```bash
cp .env.template .env
vi .env
```

# Deploy
```bash
docker stack deploy -c <(docker-compose config) prometheus
```