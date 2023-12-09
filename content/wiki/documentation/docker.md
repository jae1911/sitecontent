---
title: "Docker"
---

# Docker

This page covers the installation of Docker on Debian and a quickstart with compose.  
We will assume your Debian machine is a blank state configured with the fastest mirrors.  
It also contains a crash course to basic commands.

${toc}

## Setting Docker

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

## Basic Docker commands

Docker is extremely easy to use and contains a few basic commands:

- `docker pull <image>` - Will pull an image (if no specified repository, it will pull it from the default `hub.docker.com`)
- `docker run <image> <options/arguments>` - Will run the specified image (and pull it if not already done). This command accepts a few parameters (for the most popular):
  - `-p outsideport:insideport` - Allows to map a port from the inside of the container to the outside, for instance `-p 55:80` will make the port 80 of inside the container as available as port 50 externally
  - `-i` - Starts the container in interactive mode, which will keep STDIN open even when not attached
  - `-t` - Allocates a pseudo-TTY, basically attaches a console inside the container
  - `-e envvar=value` - Sets an environment variable inside the container
  - `-d` - Detach from the container, making it run in the background`
- `docker container ls -a` - Lists all containers
- `docker container stop <container id>` - Will stop the container
- `docker container rm <container id>` - Will remove the container
- `docker container start <container id>` - Will start the container
- `docker system prune -a` - Will clean: **all** unused images, **all** unused containers and **all** unused networks
- `docker attach <container id>` - Allows you to attach a TTY inside of the specified container

## Docker Compose

Docker Compose is a tool that allows defining and running multiple containers from a configuration file written in YAML.  
Docker Compose makes setting up services painless by automating much of the process.

For instance, let's create a simple `docker-compose.yml` file for starters:

```yaml
version: "3.9"

services:
  hello:
    image: hello-world
```

Now, if you issue `docker compose up`, you should see that the image is automatically pulled and run, showing the "Hello from Docker" message.  
The `docker compose` command also has some basic parameters:

- `up <service>` - Will bring the specified service up, note that if you don't specify a service, Compose will bring all services in the configuration file up. You will also need to add the `-d` argument to that command to not be attached to the containers when they are started
- `stop <service>` - Will stop the specified service
- `down` - Will bring down all the services specified in the Compose configuration file
- `exec <service> <command>` - Will execute the specified command in the container of the specified service
- `logs <service>` - Allows you to see the logs of a specified service, if none is specified, it will show the logs of all the services. Adding `-f` to it will follow the log like with the `tail -f` command
