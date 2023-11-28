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

// TODO

## Configuration

// TODO
