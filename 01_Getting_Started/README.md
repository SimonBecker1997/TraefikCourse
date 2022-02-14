# Getting Started with traefik

This lab lets you start traefik for the first time. 
To start traefik:
1. Navigate to this directory
2. Run `docker-compose up`

Now you have started traefik successfully.
Go now to `localhost:8080` and open the traefik dashboard.
Check also out the `traefik.yml`. The traefik.yml is the current configuration file. You can adjust the configs inside `traefik.yml` for example the loglevel or the entrypoint.

Now open `whoami.localhost` in your browser. You will see a webpage which shows the current container ID.

You can also play around by scaling the containers of whoami service up by running 
```
docker-compose up --scale whoami=3
```
Now open `whoami.localhost` again and refresh the page a couple of times. You will see that the hostname values are changing. 
Traefik routes the requests and forwards them to any whoami container running.

## How to configure traefik
There are multiple ways to configure traefik.
In the `docker-compose.yml` we have 2 ways to set the traefik settings:
### Via commands:
```
services:
  reverse-proxy: 
    image: traefik:v2.4
    command: --api.insecure=true --providers.docker
```
This is recommended to just try traefik out.

### Traefik.yml
This is the preferred way to configure traefik. 
to activate the traefik.yml, mount it to the following directory:
```
    volumes:
      - ./traefik.yml:/etc/traefik/traefik.yml
```
