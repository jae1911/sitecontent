---
title: "Resonite"
---

# Resonite

Random documentation about Resonite.

## Useful Links

- [Resonite website](https://resonite.com)
- [Resonite moderation](https://moderation.resonite.com)
- [Resonite issues](https://github.com/Yellow-Dog-Man/Resonite-Issues/)
- [Resonite Discord Guild](https://discord.gg/resonite)

## Resonite Bot commands

### Basic commands

- `/addHearingImpaired` - Adds the hearing impairment badge
- `/removeHearingImpaired` - Removes the hearing impairment badge
- `/addColorBlind` - Adds the colorblind badge
- `/removeColorBlind` - Removes the colorblind badge
- `/addVisuallyImpaired` - adds the visual impairment badge
- `/removeVisuallyImpaired` - Removes the visual impairment badge
- `/addMute` - Adds the mute badge
- `/removeMute` - Removes the mute badge
- `/addPotato` - Adds the potato badge (low end machines)
- `/removePotato` - Removes the potato badge
- `/requestRecordUsageReport` or `/requestRecordUsageJSON` - Sends you an email with what storage is your full inventory using in plaintext or JSON format
- `/deleteRecord <id>` - Deletes the specified record ID
- `/enableLogin2FA` - Enables 2FA on login
- `/disableLogin2FA` - Disables login 2FA
- `/changeUsername <old username> <new username>` - Changes your username (can only be used once every 7 days)
- `/serverinfo` - Displays some information about the server like the current uptime, Linux version and runtime version

### Patreon only

- `/addExitMessage <message>` - Submits an exit message
- `/listExitMessages` - Lists your submitted exit messages
- `/shareStorageWithGroup <group> <amount>` or `/shareStorageWithUser <user> <amount>` - Shares the specified amount of storage with a user or group
- `/set2DBadge <resdb:/// URL>` or `/set3DBadge <record URL>` - Sets your 3D or 2D badge (3D badge limitations are 128 tris, 256 verts); custom badges have some limitations:
  - 3D badges must be one mesh renderer, one static mesh (up to 128 triangles **or** 256 vertices) and a single texture (auto resized to 128px)
  - Only the following components are allowed on the badge:
    - `StaticTexture2D`
    - `StaticMesh`
    - `StaticShader`
    - `MeshRenderer`
    - `Spinner`
    - `Wiggler`
    - `Panner1D` -> `Panner4D`
    - Materials 
- `/clear2DBadge` or `/clear3DBadge` - Removes your set 3D or 2D badge
- `/createGroup <groupname>` - Create a new group with the specified group name
- `/getGroupInfo <groupname>` - Gets all the info about a group (requires you to be the admin of said group)
- `/addMember <groupname> <username> <quota>` - Adds a player to a group
- `/removeMember <groupname> <username>` - Removes a player from a group
- `/priorityIssue <issue ID>` - Sets a GitHub issue as a priority
- `/requestDeleteRecovery <time period> <name search>` - Starts the recovery of a deleted record matching a certain name under a certain time period
- `/headlessCode` - Displays the headless access code

## Command line launch arguments

Those launch arguents are to be added either to Steam or any shortcut that you might have to the Resonite executable.  
Pictured below, example of Steam command line launch arguments.

![Steam game property window with at the bottom some launch arguments.](https://i.j4.lc/ShareX/2023/10/steamwebhelper_BR3O5QVVbB.png)

- `-Invisible` - Starts your game with the "invisible" status by default
- `-ForceSRAnipal` - Forces SRanipal to be launched (face tracking)
- `-LoadAssembly` - Loads additional plugins
- `-ResetDash` - Resets your dashboard /!\ Will remove all your facets /!\
- `-SteamVR` - Launches the game with SteamVR
- `-RiftTouch` - Launches the game with Oculus rift + touch controllers
- `-Screen` - Launches the game in desktop mode
- `-Screen360` - Launches the game in desktop mode with 360 projection on
- `-SkipIntroTutorial` - Skips the tutorial on first uninitialized game launch
- `-DoNotAutoLoadHome` - Avoids loading your cloud home
