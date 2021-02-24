# bezorgzorg
Run `docker-compose up -d` to launch discourse + postgres + redis

Run `docker-compose exec discourse /bin/sh` to open a shell to the discouse container. Create an admin account with these commands.

```bash
cd /opt/bitnami/discourse
RAILS_ENV=production bundle exec rake admin:create
```
