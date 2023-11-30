---
title: 'Miscellaneous'
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

- Restart your game
- Disable mods and plugins if you use any (remove `-LoadAssembly` from your launch arguments)
- Make sure you are on the latest version; if an update just came out and you don't get it, you have two ways of forcing the update:
  1. Restart steam fully
  2. Right click on Resonite and go to "Properties", then "Installed Files" and click on "Verify integrity"
- If your issue concerns the dashboard, you can try launching the game with the `-resetDash` launch argument **WARNING, THIS WILL COMPLETELY RESET YOUR DASHBOARD AND ANY FACETS PUT ON IT**

One other thing to keep in mind are the minimal specifications required for Resonite, which you can find [on the Steam page](https://store.steampowered.com/app/2519830/Resonite/).  
For instance, playing Resonite on a 15 years old entry-level laptop will not work.
