# Routing
This chapter show you how to route requests to your containers by defining rules in traefik.
To run the lab:
1. Navigate in your command prompt to this directory.
2. Run `docker-compose up`

This lab shows you
* How to create rules
* How to define to which container and port your request should be routed to
* How traefik handles paths

If you open the `docker-compose.yml` with any text editor, you will notice that there are 4 webservices defined. They all send on a different port. 
We created for all of them a URL. 
* Webserver1: webserver1.localhost
* Webserver2: webserver2.localhost
* Webserver3: webserver3.localhost
* Webserver4: webserver4.localhost

Check out the traefik dashboard under `localhost:8080` and explore how the settings we set as labels in docker-compose are showing up there.

## How the routing works
You can define on each container you would like to route the traffic to a label.
The label defines on which URL the container should reply to
```
    labels: 
      - "traefik.http.routers.webserver1.rule=Host(`webserver1.localhost`)"
```
You can also define ports. If your container runs on port 8000, don't forget to define this in the labels as well:
```
    labels: 
      - "traefik.http.routers.webserver1.rule=Host(`webserver1.localhost`)"
      - "traefik.http.services.webserver1.loadbalancer.server.port=8000"
```
