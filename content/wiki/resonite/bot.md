---
title: "Resonite Bot"
---

# Resonite Bot

The Resonite bot can be found in your contacts list by default and commands can be sent to it to do various things like assign yourself badges or get the headless beta code.

${toc}

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
- `/setPrimaryEmail <email>` | `/addAlternateEmail <email>` - Either changes your main account email or adds a new alternative one (useful if your Patreon email doesn't matches your Resonite one)

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
  - Note: the quota is how many GBs a particular user can access of the full storage of the group. Setting it to `-1` means the member can use as much storage as they want. Groups are limited to 10G by default.
- `/removeMember <groupname> <username>` - Removes a player from a group
- `/priorityIssue <issue ID>` - Sets a GitHub issue as a priority
- `/requestDeleteRecovery <time period> <name search>` - Starts the recovery of a deleted record matching a certain name under a certain time period
- `/headlessCode` - Displays the headless access code

### Cloud variables

See [Working with Cloud Variables](/wiki/resonite/cloudvars#working-with-cloud-variables).
