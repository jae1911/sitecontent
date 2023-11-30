---
title: "Miscellaneous"
---

# Miscellaneous

Random stuff too small to be in its own category.

${toc}

## Downloading your account data

In accordance to GDPR article 20, you have a right to download the data you provided.  
For this, a tool was created and is located in your Resonite folder, under `Tools` and `Accountdump`.

To run the AccountDump program, you will need some dependencies:

- [.NET Runetime 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)

Downloading your account is pretty simple and there is two ways of launching the account dumper:

1. Double click the executable `AccoutDump.exe` and a window should pop up
2. Open a terminal in the `AccountDump` directory and do this command: `dotnet AccountDump.dll`

The account dumper will ask you for some information:

- Your Resonite username
- Your Resonite password
- Your Resonite 2FA code (if enabled on your account)
- A path in which your account data will be put (for instance `C:\Users\me\Downloads\ResoniteAccount`)

Upon entering that information, the AccountDumper will automatically begin and start downloading your account data.  
Depending on the size of your account, the tool might take more or less time to finish.

There is currently no official tool to upload that account data back into Resonite.

## Basic troubleshooting

Before opening an issue on the GitHub about a bug, it is good to do a bit of troubleshooting.

### General

- Restart your game
- Disable mods and plugins if you use any (remove `-LoadAssembly` from your launch arguments)
- Make sure you are on the latest version; if an update just came out and you don't get it, you have two ways of forcing the update:
  1. Restart steam fully
  2. Right click on Resonite and go to "Properties", then "Installed Files" and click on "Verify integrity"
- If your issue concerns the dashboard, you can try launching the game with the `-resetDash` launch argument **WARNING, THIS WILL COMPLETELY RESET YOUR DASHBOARD AND ANY FACETS PUT ON IT**

One other thing to keep in mind are the minimal specifications required for Resonite, which you can find [on the Steam page](https://store.steampowered.com/app/2519830/Resonite/).  
For instance, playing Resonite on a 15 years old entry-level laptop will not work.

### Database

Sometimes, while playing, you might get a message saying "Database Corrupted".  
Here are some steps to fix that issue:

- Make sure you have enough space on your main drive (`C:`) or the one Resonite data and cache are
  - Try to keep at least 20GB free on that drive to have a good margin
  - To free space, you can delete your cache folder which is located by default in `C:\Users\<user>\AppData\Local\Temp\Yellow Dog Man Studios\Resonite` ; there, delete the `Cache` folder
- Try to repair the database by launching the game with the `-repairDatabase` launch argument

Sometimes, doing those steps isn't enough and there is the nuclear option left.  
**Before proceeding, make sure you:**

- Free space on your drive
- Tried to repair the database
- Understand that deleting the database will:
  - Lead to data loss:
    - Resetting the local home
    - Resetting settings
    - Deleting anything not fully synced with the cloud
  - Will log you out
  - Will reset your MachineID
  - Will require you to redo the tutorial (unless Resonite is launched with the `-SkipIntroTutorial` launch argument)

To completely remove your database, the steps are as follows:

- Go to `%USERPROFILE%\AppData\LocalLow\` in a file manager
- Find the `Yellow Dog Man Studios` folder
  - It is recommended to backup that folder before deleting it, _just in case_
- Delete the `Yellow Dog Man Studios` folder
- Restart Resonite

Remember that doing that is exceptional and that most issues can be resolved without touching the database at all.
