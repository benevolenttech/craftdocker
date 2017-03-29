# craftdocker

A Craft base running on sealink/phpdocker

*   uses php7-fpm & nginx
*   uses imageMagick and php-redis
*   uses pansophy to setup configuration files during deployment


## Changes in Fork

*   Uses localhost:8080 instead of craft.dev:80, because osx doesn't like that
*   Uses a local development folder on the host for craft files


## Setup

If you want to update the craft version update the Dockerfile with http://craft.dev/craftversion.txt

### Installing:

Open a terminal:

```bash
git clone https://github.com/benevolenttech/craftdocker.git craft-1
cd craft-1
docker-compose build  # this takes ~10m with a good rig
docker-compose up
```

The webserver and mysql are now running.

In another terminal, prime your local development folder at approotmount

```bash
docker exec -i -t `docker ps --filter name=testbest_web -q` /bin/bash -c "cp -rfp /app_orig/* /app”
```

## Running

```bash
cd craft-1
docker-compose up
```

Rock and roll!

