# bezorgzorg

## Launch discourse
Run `docker-compose up -d` to launch discourse + postgres + redis

Run `docker-compose exec discourse /bin/sh` to open a shell to the discouse container. Create an admin account with these commands.

## Create discourse admin

```bash
cd /opt/bitnami/discourse
RAILS_ENV=production bundle exec rake admin:create
```

## Request SSL certificate
copy nginxsite.conf to /etc/nginx/sites-available, link to it in /sites-enabled and run:

```bash
apt-get update
sudo apt-get install certbot
apt-get install python-certbot-nginx
sudo certbot --nginx -d example.com -d www.example.com
```
