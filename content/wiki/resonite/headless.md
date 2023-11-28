---
title: "Headless client"
---

# Headless client

The headless client is basically the game without the user interface, allowing you to host _somewhat_ permanent sessions, like with a server.  
In order to access the headless client, you need to be a supporter on the [Resonite Patreon](https://patreon.com/resonite) with a membership of Discoverer or more.

${toc}

## Downloading the headless client

> Note: before proceeding, I can recommend creating a dedicated Steam account for the headless. Doing so will make it easy to automate the process with Docker or scripts later.

### Baremetal

To obtain the headless, you currently will need [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) and the headless beta code (can be obtained by sending `/headlessCode` to the Resonite bot).

> Note: it is also possible to download the headless using the regular GUI Steam client, for that right click on Resonite, select "Properties", go in "Betas" and enter the headless code into the text box. You should now have access to the headless client.

With SteamCMD, the command is fairly simple (note, it will install Resonite in the SteamCMD directory, you can change the path of the `+force_install_dir` to change that):

```bash
bash steamcmd.sh \
    +force_install_dir ./resonite \
    +login SteamAccountName 'SteamAccountPassword' \
    +app_license_request 2519830 \
    +app_update 2519830 -beta headless -betapassword TheHeadlessCode validate \
    +quit
```

This will install the headless client into the directory specified, you can now go on to the [configuration](#configuration).  
To run the headless client, you can go within the directory and do `mono Headless/Resonite.exe` and the headless should launch.

### Docker

To run a headless within Docker, I can recommend Shadowpanther's [resonite-headless](https://github.com/shadowpanther/resonite-headless).  
It is fairly easy to use.

As specified in the README, the compose file should look like this:

```yaml
version: "3.3"

services:
  resonite:
    image: shadowpanther/resonite-headless:latest
    container_name: resonite-headless
    tty: true
    stdin_open: true
    environment:
      STEAMBETA: headless
      STEAMBETAPASSWORD: ask-bot-for-code
      STEAMLOGIN: "your_steam_login your_steam_password"
    volumes:
      - "./Config:/Config:ro"
      - "./Logs:/Logs"
      - "/etc/localtime:/etc/localtime:ro"
    restart: unless-stopped
```

Now that you have this setup, you can proceed to the [configuration](#configuration) section.  
Launching the headless is as easy as `docker compose up -d` and `docker compose logs` to see logs (add `-f` to it to follow them in realtime).

## Configuration

// TODO
