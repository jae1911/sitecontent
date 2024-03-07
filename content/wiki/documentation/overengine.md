---
title: "Getting started with Overengine"
---

# Getting started with Overengine

This article will describe how to get started and host your own instance of Overengine.

## Production setup

Currently, only Docker is supported, baremetal deployments are deprecated.

### Docker

You will need:

- Docker (19.03.0+) (see [installation instructions here](/wiki/documentation/docker))

Create the following Compose file:

```yml
version: "3.8"

services:
  overengine:
    image: d.j4.lc/general-stuff/overengine:beep
    ports:
      - "127.0.0.1:8080:8080"
```

In theory, you should be good to go and run it, but it will run it in debug mode which is suboptimal for real deployments.  
For a more better Compose file, you can use:

```yml
version: "3.8"

services:
  overengine:
    image: d.j4.lc/general-stuff/overengine:beep
    ports:
      - "127.0.0.1:8080:8080"
    env_file:
      - .overengine.env
    volumes:
      - ./content:/content
```

With the following `.overengine.env` file:

> Note: `/content` assumes a clone of the [site-content](https://g.j4.lc/general-stuff/site-content) repo

```
CONTENT_DIR=/content/content
NODE_ENV=production
```

Congrats, you have now a running version of Overengine.  
Proceed to the [configuration](#configuration) section of this page for more information.

It is also recommended to use a reverse proxy such as [Caddy](https://caddyserver.com/) to have HTTPS on the site.

## Dev setup

Setting up a dev repo is pretty simple:

```
git clone https://g.j4.lc/general-stuff/overengine.git
cd overengine
git submodule update --init
yarn
yarn dev
```

This should launch a development server on `http://localhost:8080` ready to be used.

### Docker

To build a local Docker image, use:

```
docker build -t overengine:latest .
```

## Configuration

There are multiple configuration keys in Overengine, all set through the environment variables.  
Here is a table of all of them.

| Name                   | Description                                     | Example                        |
| ---------------------- | ----------------------------------------------- | ------------------------------ |
| CONTENT_DIR            | Sets the location of the content of the website | CONTENT_DIR=/content           |
| SITE_NAME              | The name of your site                           | SITE_NAME=Awa Awa              |
| SITE_DESCRIPTION       | The description of your site                    | SITE_DESCRIPTION=Awa Kabawa    |
| SITE_TAGLINE           | The site subtitle/tagline                       | SITE_TAGLINE=Beep              |
| SITE_COPYRIGHT         | The site's copyright line                       | SITE_COPYRIGHT=CC BY-SA 4.0    |
| SITE_LANGUAGE          | The site language code                          | SITE_LANGUAGE=eo               |
| DOMAINS_ADVERTISED     | Domains you wish to advertise on the sidebar    | DOMAINS_ADVERTISED=example.com |
| MATRIX_SUBDOMAIN       | Used to set a Matrix server subdomain           | MATRIX_SUBDOMAIN=matrix        |
| MATRIX_HOMESERVER_PORT | Used to set a Matrix server port                | MATRIX_HOMESERVER_PORT=443     |
| MATRIX_ENABLED         | Enable Matrix well-known support                | MATRIX_ENABLED=true            |
| BLOGS_ENABLED          | Enable the blog parsing engine                  | BLOGS_ENABLED=true             |
| REDIRECTS_ENABLED      | Enable redirects                                | REDIRECTS_ENABLED=true         |
| API_ENABLED            | Enable the API                                  | API_ENABLED=true               |
