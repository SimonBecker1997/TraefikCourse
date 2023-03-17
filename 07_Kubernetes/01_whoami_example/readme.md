# How to launch the lab
## Apply all roles and permissions
One after another
```
kubectl apply -f 00-role.yml 
kubectl apply -f 00-account.yml 
kubectl apply -f 01-role-binding.yml 
```

You also can deploy all at once by running
```
kubectl apply -f 00-role.yml  00-account.yml 01-role-binding.yml 
```
## Apply traefik deployment definitions & Services
One after another
```
kubectl apply -f 02-traefik.yml 
kubectl apply -f 02-traefik-services.yml
```
Or all at once
```
kubectl apply -f 02-traefik.yml 02-traefik-services.yml
```
## Finally deploy the whoami service
```
kubectl apply -f 03-whoami.yml 
kubectl apply -f 03-whoami-services.yml 
kubectl apply -f 04-whoami-ingress.yml
```
Or all at once
```
kubectl apply -f 03-whoami.yml 03-whoami-services.yml 04-whoami-ingress.yml
```
