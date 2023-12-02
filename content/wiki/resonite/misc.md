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
- Make sure the time on your computer is synced (can cause some issues interacting with the cloud)

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

## Editing the dashboard

In Resonite, you can modify your dashboard to display more information or have new tabs through additional elements called "facets".  
To modify the facets of your dashboard, you first need to enter the dashboard UI edit mode.  
In VR, this is done by:

- On Index/Occulus, hold one of the dashboard buttons and double tap the other
- On Vive, hold both dashboard buttons until both rings fill

> Note: it is currently not possible to modify facets on desktop

Before installing a new facet, you will need to save it to your inventory, select it (by clicking once on it) and use the "Spawn Facet" button to spawn it in your userspace.  
Your userspace is what contains your dashboard and can only be seen and interacted with by you.

After spawning the facet, you can grab it with your laser and put your laser through your dashboard.  
The small squares on your dashboard should light up green if the facet can be placed there or red if it cannot.  
Once you are done editing your facets, you can exit UI edit mode by doing the same shortcuts or clicking the button on the bottom of the dashboard to do so.

## Search tools

Finding objects and content in general in Resonite can be hard to do.  
Luckily, talented members of the community made tools to facilitate that.

### RedX

RedX is a public folder indexer of which two version exists.  
Note that results might be different from the two versions.

#### AdamSkI2003's RedX+

This version is an improved version of the original one with better search parameters and a different search backend.

You can access it via:

- Your web browser, at https://redx.adamski2003.lol/
- With an in-game facet `resrec:///U-AdamSkI2003/R-7AC884DF712F5F78E4D089C995C8B7171BC6F21CA975EE37F3D3900CA82F886E`

And you can get the source at: https://github.com/AdamK2003/redx

#### MrVoltz's RedX

The good old original RedX.

You can access it via:

- Your web browser, at https://redx.cloudns.org/

And you can get the source at: https://github.com/MrVoltz/redx
