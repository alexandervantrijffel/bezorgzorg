# bezorgzorg

## Launch discourse
Run `docker-compose up -d` to launch discourse + postgres + redis

Run `docker-compose exec discourse /bin/sh` to open a shell to the discouse container. Create an admin account with these commands.

All options of the bitnami discourse docker containers are described here https://hub.docker.com/r/bitnami/discourse.

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

## Next steps
Discourse mobile react-native app: https://github.com/discourse/DiscourseMobile

Embed https://meta.discourse.org/t/embedding-discourse-comments-via-javascript/31963
