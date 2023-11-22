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

### Docker setup

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
    # OPTIONAL
    ports:
      - 8080:8080
```

### Environment options

The following options are available via ENV:

- `BASE_CONTENT_DIR` - Sets the path to the content directory; defaults to `../content/content`
- `SITE_NAME` - Sets the name of the website; defaults to `Jae's Website`
- `SITE_DESCRIPTION` - Sets the description of the website; defaults to `The blog of Jae.`
- `SITE_COPYRIGHT` - Sets the copyright information of the website; defaults to `CC BY-SA 4.0 Jae Lo Presti`
- `SITE_LANGUAGE` - Sets the language of the website; defaults to `en`
- `NODE_ENV` - Sets the production status; defaults to `null`
- `DOMAINS_ADVERTISED` - List of domains the website is served on; defaults to `null`
- `HOST` - Sets the host the website will be served from; defaults to `::`
- `REDIS_HOST` - Sets the Redis host; defaults to `null`
- `REDIS_PORT` - Sets the Redis port; defaults to `null`
- `REDIS_DB` - Sets the Redis DB; defaults to `null`
- `REDIS_PASSWORD` - Sets the Redis password; defaults to `null`
- `REDIS_USER` - Sets the Redis user; defaults to `null`
- `WAKATOKEN` - Sets the Wakatime API token; defaults to `null`
- `BGPAS` - Sets the monitoring BGP ASN; defaults to `null`
- `OWMKEY` - Sets the OWM API key; defaults to `null`
- `OWMCITY` - Sets the OWM city; defaults to `Helsinki`
- `LIGVA_DOMAIN` - Sets the Ligva API domain; defaults to `translate.jae.fi`
- `MATRIX_SUBDOMAIN` - Sets the Matrix subdomain; defaults to `null`
- `MATRIX_HOMESERVER_PORT` - Sets the Matrix port; defaults to `443`
- `MATRIX_ENABLED` - Enables Matrix utils support; defaults to `null`
- `BLOGS_ENABLED` - Enables the blog engine; defaults to `null`
- `REDIRECTS_ENABLED` - Enables redirects; defaults to `null`
- `API_ENABLED` - Enables the API utils; defaults to `null`

Now issue `docker-compose up -d` and navigate to `http://127.0.0.1:8080` and see the website.  
It is **highly recommended** to use a reverse proxy such as Caddy.
