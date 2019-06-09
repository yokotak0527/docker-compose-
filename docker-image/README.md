# BUILD DOCKER IMAGES

```
$ docker-compose build --no-cache --parallel
```

# DEVELOP DOCKER IMAGES

```
$ docker-compose up -d --build
```

# EXECUTE DOCKER CONTAINERS

```bash
# MySQL
$ docker-compose exec mysql /bin/bash
# PHP-FPM
$ docker-compose exec php /bin/sh
# Nginx
$ docker-compose exec nginx /bin/sh
```
