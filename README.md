# Composer env

This is a basic docker compose env with a traefik proxy and opentelemetry stack

## Networking

This env creates a network 'web' that other docker compose envs can use to access it services and for the proxy to connect to.

To use it add the network to services and add the following in the botton of docker compose file. Note this env must be started before other envs so the network is created
```yaml
networks:
  web:
    name: web
    external: true
```

## Opentelemetry collector
The endpoint to the collector is eithe `http://otel:4318` or `http://otel:4317` depending on protocol