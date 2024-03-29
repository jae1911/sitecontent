---
title: "Headless client"
description: "Headless client usage."
---

# Headless client

## Hey! The [official Resonite wiki is out](https://wiki.resonite.com). It means this is now unmaintained.

The headless client is basically the game without the user interface, allowing you to host _somewhat_ permanent sessions, like with a server.  
In order to access the headless client, you need to be a supporter on the [Resonite Patreon](https://patreon.com/resonite) with a membership of Discoverer or more.

[Go back to index.](/wiki/resonite/).

${toc}

## Downloading the headless client

> Note: before proceeding, I can recommend creating a dedicated Steam account for the headless. Doing so will make it easy to automate the process with Docker or scripts later.

### Bare metal

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

> Note: if SteamCMD is giving you any trouble like `steamcmd.sh: Not a directory`, replace `bash steamcmd.sh` by `./steamcmd.sh`

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

Sveken on Discord made some modifications to the compose file to accommodate for modded Resonite.  
For that, you will need to download [Resonite Mod Loader](https://github.com/resonite-modding-group/ResoniteModLoader), create a directory `moddedhead` in the data directory where you want to place the files of your headless and place inside the NML files.  
Then you can use the following compose file:

```yaml
version: "3.3"

services:
  resonite:
    image: shadowpanther/resonite-headless:latest
    container_name: modded-headless
    tty: true
    stdin_open: true
    command: mono /home/steam/resonite-headless/Headless/Resonite.exe -LoadAssembly "/home/steam/resonite-headless/Headless/Libraries/ResoniteModLoader.dll" -HeadlessConfig /Config/Config.json -Logs /Logs
    environment:
      STEAMBETA: stuff
      STEAMBETAPASSWORD: things
      STEAMLOGIN: "username password"
    volumes:
      - "/data/moddedhead/Config:/Config:ro"
      - "/data/moddedhead/Logs:/Logs"
      - "/etc/localtime:/etc/localtime:ro"
      - "/data/moddedhead:/home/steam/resonite-headless"
    restart: unless-stopped
```

This version will hijack the start script to instead run the headless with the `-loadAssembly` command, thus making it possible to run the headless with mods.

Now that you have this setup, you can proceed to the [configuration](#configuration) section.  
Launching the headless is as easy as `docker compose up -d` and `docker compose logs` to see logs (add `-f` to it to follow them in real-time).

## Configuration

The default headless configuration is as follows:

```json
{
  "$schema": "https://raw.githubusercontent.com/Yellow-Dog-Man/JSONSchemas/main/schemas/HeadlessConfig.schema.json",
  "comment": "DO NOT EDIT THIS FILE! Your changes will be lost. Copy it over and create a new file called Config.json",
  "universeId": null,
  "tickRate": 60.0,
  "maxConcurrentAssetTransfers": 4,
  "usernameOverride": null,
  "loginCredential": null,
  "loginPassword": null,
  "startWorlds": [
    {
      "isEnabled": true,
      "sessionName": null,
      "customSessionId": null,
      "description": null,
      "maxUsers": 16,
      "accessLevel": "Anyone",
      "useCustomJoinVerifier": false,
      "hideFromPublicListing": null,
      "tags": null,
      "mobileFriendly": false,
      "loadWorldURL": null,
      "loadWorldPresetName": "Grid",
      "overrideCorrespondingWorldId": null,
      "forcePort": null,
      "keepOriginalRoles": false,
      "defaultUserRoles": null,
      "roleCloudVariable": null,
      "allowUserCloudVariable": null,
      "denyUserCloudVariable": null,
      "requiredUserJoinCloudVariable": null,
      "requiredUserJoinCloudVariableDenyMessage": null,
      "awayKickMinutes": -1.0,
      "parentSessionIds": null,
      "autoInviteUsernames": null,
      "autoInviteMessage": null,
      "saveAsOwner": null,
      "autoRecover": true,
      "idleRestartInterval": -1.0,
      "forcedRestartInterval": -1.0,
      "saveOnExit": false,
      "autosaveInterval": -1.0,
      "autoSleep": true
    }
  ],
  "dataFolder": null,
  "cacheFolder": null,
  "logsFolder": null,
  "allowedUrlHosts": null,
  "autoSpawnItems": null
}
```

### Configuration keys

#### Basics

| Name                        | description                                                                                                    | type          | Required |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------- | -------- |
| comment                     | A small bit of text describing your configuration. Useful if you have multiple.                                | string        | No       |
| loginCredential             | The username for the headless client account.                                                                  | string        | Yes      |
| loginPassword               | The password for the headless client account.                                                                  | string        | Yes      |
| startWorlds                 | All the worlds to run on this headless (see the [worlds section](#worlds))                                     | Special       | Yes      |
| tickRate                    | How many updates per second should the headless do (default on 60).                                            | integer       | No       |
| maxConcurrentAssetTransfers | The maximum amount of asset transfers for the headless (default on 4)                                          | integer       | No       |
| usernameOverride            | Sets a username different from loginCredential that will be displayed in the world list and session users tab. | string        | No       |
| dataFolder                  | Sets the path to the data store.                                                                               | string        | No       |
| cacheFolder                 | Sets the path to the cache folder.                                                                             | string        | No       |
| logsFolder                  | Sets the path to the logs folder.                                                                              | string        | No       |
| allowedUrlHosts             | Lists of hosts which will be allowed for WebSocket/HTTP operations.                                            | array[string] | No       |
| universeId                  | Sets which universe the headless is in (no documentation on universes as of yet).                              | string        | No       |

#### Worlds

> Note: you can add as many worlds as you wish, just add a new one in the array.

| Name                                     | description                                                                                                                 | type          | Required | Example                                                            |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------- | -------- | ------------------------------------------------------------------ |
| sessionName                              | The name that will show up in the world browser (defaults to the world name if not present).                                | string        | No       | "awa awa"                                                          |
| customSessionId                          | Sets a custom session ID starting with `S-` and respecting the format `<userid>:<sessionid>`                                | string        | No       | "U-Awa:hangout"                                                    |
| description                              | Sets the description of the session (defaults on world description if not present)                                          | string        | No       | "Awa awa kabawa"                                                   |
| maxUsers                                 | Sets the maximum amount of users in the session (defaults to 32)                                                            | integer       | No       | 1337                                                               |
| accessLevel                              | Sets the access level of the session (Private, LAN, Friends, FriendsOfFriends, RegisteredUsers, Anyone; defaults to Anyone) | Any           | No       | RegisteredUsers                                                    |
| hideFromPublicListing                    | Hides the session (defaults on false)                                                                                       | boolean       | No       | true                                                               |
| tags                                     | List of tags to assist with discoverability.                                                                                | array[string] | No       | ["awa", "hangout"]                                                 |
| mobileFriendly                           | Is the session friendly for mobile/quest users.                                                                             | boolean       | No       | false                                                              |
| loadWorldURL                             | Loads a world to host from a `resrec:///` URL.                                                                              | string        | No       | "resrec:///G-Resonite-Team/R-c3f6fd32-d82f-4f48-80f1-87a05b184650" |
| loadWorldPresetName                      | If nothing in loadWorldURL, will create a new world following the preset.                                                   | string        | No       | "Grid"                                                             |
| overrideCorrespondingWorldId             | Overrides the world ID, allowing it to be nested with other sessions with the same world ID.                                | Any           | No       |                                                                    |
| forcePort                                | If specified, the session will run on a specific port.                                                                      | integer       | No       | 1911                                                               |
| keepOriginalRoles                        | If enabled, the headless will not override the default roles of the hosted world.                                           | boolean       | No       | true                                                               |
| defaultUserRoles                         | Sets roles for different users.                                                                                             | Object        | No       | {"j4": "Admin", "DN0": "Guest"}                                    |
| roleCloudVariable                        | Name of a cloud variable to determine user roles.                                                                           | string        | No       | "G-mygroup.headless.perms"                                         |
| allowUserCloudVariable                   | Name of a cloud variable to determine who can join the session.                                                             | string        | No       | "G-furdation.headless.whitelist"                                   |
| denyUserCloudVariable                    | Name of a cloud variable to determine who cannot join the session.                                                          | string        | No       | "G-furdation.headless.blocklist"                                   |
| requiredUserJoinCloudVariable            | Name of a cloud variable to determine if a user can join the session.                                                       | string        | No       | "G-furdation.headless.privateAccess"                               |
| requiredUserJoinCloudVariableDenyMessage | Message to display to users not on the whitelist.                                                                           | string        | No       | "You need to be verified to join this session"                     |
| awayKickMinutes                          | How many minutes can people stay AFK in the session without being kicked (-1 disables it)                                   | integer       | No       | 5                                                                  |
| saveAsOwner                              | Controls who saves this world when saved.                                                                                   | Any           | No       |                                                                    |
| autoInviteUsernames                      | Invites all the users specified to the headless on start.                                                                   | array[string] | No       | ["j4"]                                                             |
| autoInviteMessage                        | Sets a message sent before the invite to the headless is sent.                                                              | string        | No       | "Come and join!"                                                   |
| parentSessionIds                         | Provides a list of parent sessions.                                                                                         | array[string] | No       |                                                                    |
| autoRecover                              | ?                                                                                                                           | boolean       | No       |                                                                    |
| idleRestartInterval                      | Will restart the world automatically after X time elapsed if the session is empty.                                          | integer       | No       | 55                                                                 |
| forcedRestartInterval                    | Will restart the world automatically after X time elapsed no matter what.                                                   | integer       | No       | 55                                                                 |
| saveOnExit                               | If set to true, this world will be saved when shutting down the headless.                                                   | boolean       | No       | false                                                              |
| autoSaveInterval                         | Will save every X time.                                                                                                     | integer       | No       | 50                                                                 |
| autoSleep                                | Will prevent empty (or filled with away users) world to run full update cycles.                                             | boolean       | No       | true                                                               |

### Commands

There is a bunch of commands that can be used to manage the headless client within its console.

| command              | description                                                                | usage                                          |
| -------------------- | -------------------------------------------------------------------------- | ---------------------------------------------- |
| saveConfig           | Saves the current configuration into the original configuration file       | saveConfig &#60;filename>                      |
| login                | Logs into a Resonite account                                               | login &#60;username> &#60;password>            |
| logout               | Logs out of the current account                                            | logout                                         |
| message              | Sends a message to a friended user                                         | message &#60;user> &#60;message>               |
| friendRequests       | List all friend requests                                                   | friendRequests                                 |
| acceptFriendRequest  | Accepts a friend request                                                   | acceptFriendRequest &#60;user>                 |
| worlds               | List running worlds                                                        | worlds                                         |
| focus                | Focuses into the specified world (by index)                                | focus &#60;index>                              |
| startWorldURL        | Starts a world from a `resrec:///` URL                                     | startWorldURL <`resrec:///`>                   |
| startWorldTemplate   | Starts a world from a template                                             | startWorldTemplate &#60;`template`>            |
| status               | Shows the status of the current world                                      | status                                         |
| sessionURL           | Displays the session URL                                                   | sessionURL                                     |
| sessionID            | Displays the session ID                                                    | sessionID                                      |
| copySessionURL       | Copies the session URL to the clipboard                                    | copySessionURL                                 |
| copySessionID        | Copies the session ID to the clipboard                                     | copySessionID                                  |
| users                | Lists the users in the world                                               | users                                          |
| close                | Closes the current focused world                                           | close                                          |
| save                 | Saves the current focused world                                            | save                                           |
| restart              | Restarts the current focused world                                         | restart                                        |
| kick                 | Kicks a user from the sessions                                             | kick &#60;user>                                |
| silence              | Silences a user                                                            | silence &#60;user>                             |
| unsilence            | Removes the silence on a user                                              | unsilence &#60;user>                           |
| listBans             | Lists all bans                                                             | listbans                                       |
| ban                  | Bans a user                                                                | ban &#60;user>                                 |
| banByName            | Bans a user using an username                                              | banByName &#60;username>                       |
| unbanByName          | Unbans a user using an username                                            | unbanByname &#60;username>                     |
| banByID              | Bans a user using an userid                                                | banByID &#60;userid>                           |
| unbanByID            | Unbans a user using an userid                                              | unbanByID &#60;userid>                         |
| respawn              | Forces an user to respawn                                                  | respawn &#60;user>                             |
| role                 | Sets a specific role for a user                                            | role &#60;user> &#60;role>                     |
| name                 | Sets the session name for the current focused world                        | name &#60;name>                                |
| accessLevel          | Sets the session access level                                              | accessLevel &#60;level>                        |
| description          | Sets the session description for the current focused world                 | description &#60;description>                  |
| hideFromListing      | Set the focused world hidden or not                                        | hideFromListing &#60;true/false>               |
| maxUsers             | Sets the maximum amount of users                                           | maxUsers &#60;number>                          |
| awayKickInterval     | Sets the amount of time after which inactive users will be kicked          | awayKickInterval &#60;time>                    |
| import               | Imports an asset in the current focused world                              | import <resrec:/// or file path>               |
| importMinecraft      | Imports a Minecraft worl into the current focused world                    | importMinecraft &#60;path to level.dat folder> |
| dynamicImpulse       | Sends a dynamic impulse in the scene root                                  | dynamicImpulse &#60;tag>                       |
| dynamicImpulseString | Sends a dynamic impulse with string data                                   | dynamicImpulseString &#60;tag> &#60;string>    |
| dynamicImpulseInt    | Sends a dynamic impulse with int data                                      | dynamicImpulseInt &#60;tag> &#60;int>          |
| dynamicImpulseFloat  | Sends a dynamic impulse with float data                                    | dynamicImpulseFloat &#60;tag> &#60;float>      |
| spawn                | Spawns an item saved to the inventory in the root of the world             | spawn &#60;resrec:///> &#60;active true/false> |
| gc                   | Forces full garbage collection                                             | gc                                             |
| shutDown             | Shuts down the headless client                                             | shutDown                                       |
| tickRate             | Modifies the headless tickrate                                             | tickRate &#60;number>                          |
| log                  | Switches to logging mode, press enter to return to the interactive console | log                                            |
