# docker-service-proxy-example
A simple example using NGINX to reverse proxy requests to other docker containers.

## Prequisites
Make sure both [docker](https://www.docker.com/) and [docker compose](https://docs.docker.com/compose/) are installed.

## Starting the containers
Run `docker-compose up` (or `docker-compose up -d` to run in detached mode) in the root of this project. This will start 3 containers:

### proxy
This is the nginx container that contains the proxy rules to route requests to the other containers. The nginx configuration file for this container is in `proxy/nginx.conf`. The configuration file is a modified default NGINX configuration file that was copied from a running nginx container, and modified to include the proxy rules.

### app-a
All requests to `/a/` will be proxied to this container.

### app-b
All requests to `/b/` will be proxied to this container.


