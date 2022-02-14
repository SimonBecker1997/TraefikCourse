# HTTPS
SSL encryption is a must when you create a webservice. 
Thats what this lab is all about. 

To run this lab:
1. Navigate in your command prompt to this directory.
2. Run docker-compose up


This lab shows you:
* How to enable SSL
* How to forward all HTTP requests to HTTPS


1. Navigate in your command prompt to this directory.
2. Run docker-compose up
3. Now open your browser and open the following URLs:
    1. https://webserver1.localhost
    2. https://webserver2.localhost
    3. https://webserver3.localhost
    4. https://webserver4.localhost

You can see that all Webservers are now SSL encrypted.

## Configuration on how SSL
You need to enable the following settings:
### traefik.yml:
You need to link the dynamic configuration file which contains the ssl settings
```
  file:
    filename: /etc/traefik/traefik_dynamic.yml
```
Also you need to add the entrypoint for HTTPS (443)
```  
websecure:
    address: ":443"

```

### traefik_dynamic.yml
This file contains the SSL certificate config
```
tls:
  stores:
    default:
      defaultCertificate:
        certFile: /etc/traefik/certs/mycert.crt
        keyFile: /etc/traefik/certs/mycert.key
```
### docker-compose.yml
In docker-compose you need to enable the TLS setting as well as the https entrypoint which has been defined in traefik.yml
```
      - "traefik.http.routers.webserver1.entrypoints=websecure"
      - "traefik.http.routers.webserver1.tls=true"
```

## HTTP --> HTTPS forwarding
If you want to automatically forward all HTTP requests to HTTPs, add the following config to traefik.yml:
```
#Entrypoints
entryPoints:
  web:
    address: ":80"
    http:
      redirections:
        entryPoint:
          to: websecure
          scheme: https
```
