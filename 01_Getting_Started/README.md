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
