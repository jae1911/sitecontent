---
title: "OSP, the alternative to Twitch"
date: 2020-06-15T18:06:14+02:00
draft: false
description: "Today, we'll look at OSP, an alternative to Twitch and Youtube livestreams..."
tags: ["software"]
---

Not so long ago, I discovered the [Open Streaming Platform](https://openstreamingplatform.com/) (or OSP) projects that aims to bring an alternative to the website Twitch or Youtube for livestreams with a self-hosted solution.

After doing some research and asking the Tedomum team, we deployed [an instance](https://stream.tedomum.net) in order to test ourselves.  
Just like Peertube, OSP allows the user to create multiple channels without having to create multiple accounts which is practical if you want to sort your channels by topic (gaming, drawing, talk shows...).  
OSP also allows you to record automatically your streams, post videos and record clips, just like the other platforms.

The software itself was easy to run since we are using Docker & `docker-compose`. The problems we ran into were database problems, because the software is still in beta, the migration scripts are the ones by default for a flask project and are not migrating the DB correctly. If you run into this problem, you might have to downgrade the version, go to the admin panel, download a copy of the database, reset the instance with the new version and restore the database file at the installation process.  
Here is what the Dockerfile looks like (**Note: the latest revision, 0.7, is currently not supported by Docker**):

```docker
version: '2.1'

services:
  redis:
    image: redis:latest

  osp:
    image: deamos/openstreamingplatform:latest
    volumes:
      - ./data:/var/www
    labels:
      - traefik.enable=true
      - traefik.frontend.rule=Host:${hostname}
      - traefik.port=80
      - traefik.frontend.headers.STSSeconds=315360000
      - traefik.frontend.headers.browserXSSFilter=true
      - traefik.frontend.customResponseHeaders=Server:www||X-Powered-By:www
    environment:
      - REDIS_HOST=redis
      - FLASK_SECRET
      - FLASK_SALT
      - OSP_ALLOWREGISTRATION
      - OSP_REQUIREVERIFICATION
      - DB_URL=postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@db/${POSTGRES_USER}
    depends_on:
      - "db"
      - "redis"
    ports:
      - "${ipv4}:1935:1935"
      - "${ipv6}:1935:1935"

  db:
    image: postgres:11
    volumes:
      - ./db:/var/lib/postgresql/data
      - ./wal:/wal
      - ./postgresql.conf:/var/lib/postgresql/data/postgresql.conf
    environment:
      - POSTGRES_USER
      - POSTGRES_PASSWORD

networks:
  default:
    enable_ipv6: true
    driver: bridge
    ipam:
      driver: default
      config:
        - subnet: "${prefix}/80"
          gateway: "${prefix}1"
```

Also take note that postgres isn't used officially by OSP, see their wiki for the official supported databases.  
The port `1935` must be open so OBS (or any other streaming software) can send the data to `rmtp://<your domain name>/stream`

At the end, OSP is a really good piece of software, for instance, I am usually streaming (from my desktop) with a resolution of 1080p at 60 frames per second with a bitrate of 5000Kbps and OSP handles it right.  
On the releases 0.6, the devs also added an option to transcode in real-time the stream so it can be viewed in much more resultion but we didn't activated it on our instance since it consumes a shit ton of CPU.

The latest version at the time (0.7) adds a really interesting feature: the chat is now served with XMPP and other users from other XMPP servers can join and interract with the chat without needing an account on the instance. Sadly, as said earlier, this release isn't 'Docker-ready' yet so we'll have to play the waiting game.

For me OSP is a project you need to follow closely if you are into streaming but also want to be able to share your content on libre platforms.

That's all for today,
I'll se you next time!
