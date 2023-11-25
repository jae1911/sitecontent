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

**Did I miss something? Is something wrong? Please do contact me to correct it or open a PR on the sitecontent!**  
Help is very much welcomed, especially on fields where the description is marked as `??`.

## Reporting bugs

Here is what you can do to diagnose and report bugs:

1. Update your game to the latest version
2. Disable mods
3. If you bug concerns the dashboard, try to start the game with `-resetDash`
4. Create GitHub issue

I can recommend trying to find a way to reproduce the bug before, then doing a clean launch, reproducing the bug immediately and closing the game in order to have clean logs for the report.

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

### Most common

- `-Invisible` - Starts your game with the "invisible" status by default
- `-ForceSRAnipal` - Forces SRanipal to be launched (face tracking)
- `-LoadAssembly <path>` - Loads additional plugins
- `-ResetDash` - Resets your dashboard /!\ Will remove all your facets /!\
- `-SteamVR` - Launches the game with SteamVR
- `-RiftTouch` - Launches the game with Oculus rift + touch controllers
- `-Screen` - Launches the game in desktop mode
- `-Screen360` - Launches the game in desktop mode with 360 projection on
- `-SkipIntroTutorial` - Skips the tutorial on first uninitialized game launch
- `-DoNotAutoLoadHome` - Avoids loading your cloud home
- `-RepairDatabase` - Repairs the database
- `-forceNoVoice` - Disables voice
- `-data <path>` | `-dataPath <path>` - Sets the data storage path
- `-logs <path>` | `-logsPath <path>` - Sets the logs path
- `-cache <path>` | `-cachePath <path>` - Sets the cache path
- `-deleteUnsyncedCloudRecords` - Deletes records that couldn't be synced at the last closure /!\ Might lead to data loss /!\
- `-forceSyncConflictingCloudRecords` - Forces syncing of conflicting records /!\ Might lead to data loss /!\

### The rest

- `-ctaa` - ??
- `-ctaaTemporalEdgePower <num>` - ??
- `-ctaaSharpnessEnabbled <num>` - ??
- `-ctaaAdaptiveSharpness <num>` - ??
- `-enableOwO <IP>` - Sets the IP for the OwO haptics suit
- `-legacySteamVRInput` - Reverts inputs to the legacy SteamVR method
- `-etee` - ??
- `-device <Autodetect|Headless|Screen|Screen360|StaticCamera|StaticCamera360|SteamVR|WindowsMR|Oculus|OculusQuest>` - Sets the output device (defaults to `Autodetect`)
- `-forceRelay` - Force the use of the LNL relay
- `-forceSRanipal` - Force the use of SRanipal
- `-cameraBiggestGroup` - ??
- `-cameraTimelapse` - ??
- `-cameraStayBehind` - ??
- `-cameraStayInFront` - ??
- `-forceReticleAboveHorizon` - ??
- `-useAppCamera` - ??
- `-forceIntroTutorial` - Force start the tutorial on startup
- `-OnlyHost <user>` - ??
- `-join <Auto | <Session>>` - Auto joins a session from URI
- `-open <uri>` | `-OpenUnsafe <uri>` - Auto starts a world from URI (??)
- `-noUI` - Disables UI display
- `-kiosk` - Starts the game in Kiosk mode
- `-bench <uri>` - ??
- `-resetUserSpace` - Resets user space
- `-forceLANOnly` - Makes it so the game can only join LAN worlds
- `-watchdog` - ??
- `-bootstrap <Assembly.dll>` - ??
- `-mixedReality` - ??
- `-directComposition` - ??
- `-externalComposition` - ??
- `-create_mrc_folder` - ??
- `-load-mrc-config` - ??
- `-exportDatabaseAll <path>` - Exports everything found in the database to the specified path
- `-exportDatabaseEngine <path>` - Exports records owned by local machine to the specified path
- `-disableNativeTextureUpload` - ??
- `-cubemapResolution <num>` - Sets the cubemap resolution
- `-screen` - Starts the game in desktop mode
- `-Verbose` - Enables verbose logging
- `-cloudProfile <Production|Staging|Local>` - Sets server (??)
- `-engineConfig <config.json>` | `-engienConfigFile <config.json>` - Sets the config location
- `-priorityWorkers <num>` - Sets the number of priority workers
- `-GeneratePreCache` - ??
- `-BackgroundWorkers` - ??
