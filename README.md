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
set -a
. ./.env
set +a

# Verify that rendered paths, hostnames, labels, and stack-specific names come from this repository's .env.
docker-compose --env-file .env config

# Deploy only after the rendered config is correct.
docker stack deploy -c <(docker-compose --env-file .env config) prometheus
```