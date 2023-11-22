---
title: "Getting started with Overengine"
---

# Getting started with Overengine

This article will describe how to get started and host your own instance of Overengine.

## Building the software

You will need to [install the Docker daemon](/wiki/documentation/docker).  
To build the software, clone it:

```bash
git clone https://git.sr.ht/~jae/Overengine
cd Overengine
```

And then build it:

```bash
docker build -t overengine .
```

> Note: you can build it for your own package registry

```bash
docker login reg.domain.tld
docker build -t reg.domain.tld/username/overengine
docker push reg.domain.tld/username/overengine
```

This will allow you to pull it from a remote server: `docker pull reg.domain.tld/username/overengine`

## Deployment

For deployment, `docker-compose` is used.

Put your website content in the `content/` folder at the same level of the compose file.  
You can create a `docker-compose.yml` with the following contents (change the token secrets accordingly):

```yaml
version: "3.9"

services:
  redis:
    image: redis

  overengine:
    volumes:
      - ./content:/content
    environment:
      - BASE_CONTENT_DIR=/content
      - SITE_NAME=My website
      - NODE_ENV=production
      - REDIS_HOST=redis
      - WAKATOKEN=secret
      - OWMKEY=secret
      - OWMCITY=Annecy
    # OPTIONAL
    ports:
      - 8080:8080
```

Now issue `docker-compose up -d` and navigate to `http://127.0.0.1:8080` and see the website.  
It is **highly recommended** to use a reverse proxy such as Caddy.
