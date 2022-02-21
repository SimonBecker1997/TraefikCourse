# Monitoring and Logging
You need to know whats happening when you operate a webapp or any webservice. A crucial part is also the rerverse proxy (in this example traefik).
This lab show's you how to start monitoring traefik. 
We will have a look at
* Logging
* Traces
* Metrics


### To start the monitoring environment:
Navigate to the elk directory:
    ```
    cd elk
    ```
 
Start the Elastic containers by running  
 ```
 docker-compose up -d
```
The `-d` option allows you to run it in the background. 
To stop it after use, simmply navigate again in the elk directory and run `docker-compose down`

After starting the ELK service, launch the traefik instance which ich in this directory
```
docker-compose up
```

