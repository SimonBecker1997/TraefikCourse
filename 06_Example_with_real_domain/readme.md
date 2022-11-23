# Traefik example on server exposed to internet with domain
## Precondition
You need a webserver with a domain.  
You can get domains at many different providers.  
I use digital ocean as my cloud service, so I chose a domain from these resellers: https://docs.digitalocean.com/tutorials/dns-registrars/  
You can get a digital Ocean account for 5$ via Paypal. Then you can get a free 200$ offer. Note: you can use my referral link to get the 200$ for free:   

[![DigitalOcean Referral Badge](https://web-platforms.sfo2.cdn.digitaloceanspaces.com/WWW/Badge%201.svg)](https://www.digitalocean.com/?refcode=bafc3d30d978&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge)

## Use traefik with domain
1. Link domain to your server
2. Clone the repository to your server
3. Edit the domain name in the `docker-compose.yml`
4. Run the docker-compose file by typing `docker-compose up`
