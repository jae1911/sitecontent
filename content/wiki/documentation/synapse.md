---
title: "Setting up your on Matrix server using Synapse"
---

# Setting up your on Matrix server using Synapse

Greetings everybody.  
Today, we're gonna learn how to setup your own Matrix server using [Synapse](https://github.com/matrix-org/synapse).

Pre-requisites:
 - Some time
 - A server (preferably Debian)
 - [Docker installed](/wiki/documentation/docker)
 - A reverse-proxy (in this example, [Caddy](https://caddyserver.com))
 - A domain/subdomain (as long as you can host a `.well-known` on the domain)

Caddy is used here because of its ease of use and maintenance (auto-renews and requests SSL for instance & super easy config files).

## DNS Setup

First, setup your root to your server and also the `matrix` subdomain.  
The zone should look like this (replace the IPs by yours or use the web panel of your domain; dummy addresses from my own network are shown):
```dns
@ 300 IN A 88.218.40.1
@ 300 IN AAAA 2001:67c:2724:e000:b::1
matrix 300 IN A 88.218.40.1
matrix 300 IN AAAA 2001:67c:2724:e000:b::1
```

## Compose setup

Setting up a Matrix server is really simple.  
There, we will setup:
 - The Matrix server itself
 - The reverse proxy

The `docker-compose.yml` file will look something like this:
```yml
version: "3.9"

services:
  caddy:
    image: caddy:2
    volumes:
      - ./caddy/data:/data
      - ./caddy/web:/web
      - ./caddy/Caddyfile:/etc/caddy/Caddyfile:ro
    ports:
      - 80:80
      - 443:443
    
  synapse:
    image: matrixdotorg/synapse
    volumes:
      - ./synapse:/data
```

## Generation of the server

After creating this file, we can generate the configuration and keys for the actual server:

```bash
docker run -it --rm \
    -v $(pwd)/synapse:/data \
    -e SYNAPSE_SERVER_NAME=my.tld \
    -e SYNAPSE_REPORT_STATS=no \
    matrixdotorg/synapse:latest generate
```

Also, edit the `synapse/homeserver.yaml` file and set the following config to avoid people registering on your personal server:
```yaml
enable_registration: false
```

## Reverse proxy configuration

Then, let's create the reverse proxy configuration (in `caddy/Caddyfile`):
```caddyfile
https://my.tld {
    root * /web/website
    file_server
}

https://matrix.my.tld {
    reverse_proxy synapse:8008
}
```

Now you can create `caddy/web/website` and put your website into it.  
You will also have to create the directory `.well-known` with `mkdir -p caddy/web/website/.well-known/matrix` and now, edit `caddy/web/website/.well-known/matrix` to contain:
```json
{
    "m.server": "matrix.my.tld:443"
}
```

## First run

To start your newly created server, you just have to issue `docker compose up -d`.  
You can use the [Matrix federation tester](https://federationtester.matrix.org) to test if your server federates correctly.

If so, to register a user, you can issue these commands:
```bash
docker compose exec synapse bash
register_new_matrix_user -c /data/homeserver.yaml http://localhost:8008
```

Follow the on-screen prompt and register your user.

**All done, you can now talk with other Matrix servers!**
