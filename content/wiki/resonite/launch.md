---
title: "Launch arguments"
---

# Launch Arguments

Resonite can be launched with a number of arguments.  
To use them, all you have to do is right click on Resonite on Steam, select "properties" and add your launch arguments to the text box.

![Steam game property window with at the bottom some launch arguments.](https://i.j4.lc/ShareX/2023/10/steamwebhelper_BR3O5QVVbB.png)

${toc}

## Most common

- `-Invisible` - Starts your game with the "invisible" status by default
- `-ForceSRAnipal` - Forces SRanipal to be launched (face tracking)
- `-LoadAssembly <path>` - Loads additional plugins
- `-ResetDash` - Resets your dashboard /!\ Will remove all your facets /!\
- `-SteamVR` - Launches the game with SteamVR
- `-RiftTouch` - Launches the game with Oculus rift + touch controllers
- `-Screen` - Launches the game in desktop mode
- `-SkipIntroTutorial` - Skips the tutorial on first uninitialized game launch
- `-DoNotAutoLoadHome` - Avoids loading your cloud home
- `-RepairDatabase` - Repairs the database
- `-forceNoVoice` - Disables voice
- `-data <path>` | `-dataPath <path>` - Sets the data storage path
- `-logs <path>` | `-logsPath <path>` - Sets the logs path
- `-cache <path>` | `-cachePath <path>` - Sets the cache path
- `-deleteUnsyncedCloudRecords` - Deletes records that couldn't be synced at the last closure /!\ Might lead to data loss /!\
- `-forceSyncConflictingCloudRecords` - Forces syncing of conflicting records /!\ Might lead to data loss /!\

## The rest

- `-Screen360` - Launches the game in desktop mode with 360 projection on
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