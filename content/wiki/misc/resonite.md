---
title: "Resonite"
---

# Resonite

Random documentation about Resonite.

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
- `/webLogin` - Temporarily stop asking for 2FA to be able to login on the accounts website

### Patreon only

- `/addExitMessage <message>` - Submits an exit message
- `/listExitMessages` - Lists your submitted exit messages
- `/shareStorageWithGroup <group> <amount>` or `/shareStorageWithUser <user> <amount>` - Shares the specified amount of storage with a user or group
- `/set2DBadge <badge URL>` or `/set3DBadge <record URL>` - Sets your 3D or 2D badge (3D badge limitations are 128 tris, 256 verts)
- `/clear2DBadge` or `/clear3DBadge` - Removes your set 3D or 2D badge
- `/createGroup <groupname>` - Create a new group with the specified group name
- `/getGroupInfo <groupname>` - Gets all the info about a group
- `/addMember <groupname> <username> <quota>` - Adds a player to a group
- `/removeMember <groupname> <username>` - Removes a player from a group
- `/priorityIssue <issue ID>` - Sets a GitHub issue as a priority
- `/requestDeleteRecovery <time period> <name search>` - Starts the recovery of a deleted record matching a certain name under a certain time period

Note: the `/getGroupInfo` command is also available to non-Patreons under the condition that they are part of the group they are querying.
