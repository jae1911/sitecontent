---
title: "Setting up Docker on Debian"
---

# Setting up on Docker

This page covers the installation of Docker on Debian and a quickstart with compose.  
We will assume your Debian machine is a blank state configured with the fastest mirrors.

## Setting up the base Docker

Everything there needs to be run as room (you can use `sudo` for most commands).  
Update your system with `apt update` and then install prerequisites `apt install ca-certificates curl gnupg lsb-release`.

Add the Docker PGP key:
```bash
mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

And then add the repo:
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Now, update and install Docker itself `apt update; apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin`  
This will install the base of Docker but also the `docker-compose` plugin that we will use later.

Now enable and start Docker and you're all set:
```bash
systemctl enable docker
systemctl start docker
```

## Sample docker-compose

Create a file named `docker-compose.yml` and inside:
```yaml
version: "3.9"

services:
  hello:
    image: hello-world
```

Now you can run `docker compose up` and see the hello world.
