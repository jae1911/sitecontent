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

Downloading your account is pretty simple and there is two ways of launchning the account dumper:

1. Double click the executable `AccoutDump.exe` and a window should pop up
2. Open a terminal in the `AccoutDump` directory and do this command: `dotnet AccountDump.dll`

The account dumper will ask you for some information:

- Your Resonite username
- Your Resonite password
- Your Resonite 2FA code (if enabled on your account)
- A path in which your account data will be put (for instance `C:\Users\me\Downloads\ResoniteAccount`)

Upon entering that information, the AccountDumper will automatically begin and start downloading your account data.  
Depending on the size of your account, the tool might take more or less time to finish.

There is currently no official tool to upload that account data back into Resonite.
