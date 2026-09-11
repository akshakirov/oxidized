```
cd /opt/

git clone https://github.com/akshakirov/oxidized.git

htpasswd /opt/oxidized/nginx/.htpasswd USERNAME
```

Change yourdomain.com to your domain
```
./nginx/oxidized.conf:    server_name oxidized.yourdomain.com;
./nginx/oxidized.conf:    ssl_certificate     /etc/letsencrypt/live/oxidized.yourdomain.com/fullchain.pem;
./nginx/oxidized.conf:    ssl_certificate_key /etc/letsencrypt/live/oxidized.yourdomain.com/privkey.pem;
./docker-compose.yml:      DOMAIN: oxidized.yourdomain.com
./docker-compose.yml:      EMAIL: noc@yourdomain.com
```

Set your cloudflare token in secrets/cloudflare.ini

and start it with ```docker compose up -d```


Don't forget to enter a creditenials in config/routers.db to match your equipment
```
username: net-equipment-readonly-user
password: VeryStrongPassw0rd
```
