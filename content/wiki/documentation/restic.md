---
title: "Using restic"
---

# Using restic

I use Restic on all my machines to make backups, it's really practical.  
I use the software with a S3 bucket.

## Setting up the repo

First, go on your S3 solution (be it Minio, Wasabi or others) and create a new bucket named something like `backups` (or anything you want, really).  
Then, generate credentials for the said bucket and you're all set to begin.

First, we need to initialize the repo:

```
export AWS_ACCESS_KEY_ID=myaccesskey
export AWS_ACCESS_KEY_ID=iamverysecure
restic -r s3:s3.server.tld/backups/<my app/server name> init
```

You will have to choose a password during this process, I recommend using a passfile when using the software in later stages (usually `/sec/pass` in my commands).

You now have an initialized repository!

## Tips

If you use the root bucket: `s3:s3.server.tld/backups` it will create only one repo per bucket.  
If you wish to create multiple repos per bucket, just add the name of your app/server at the end of the path and it will create a new repo in the bucket: `s3:s3.server.tld/backups/app` (creates a repo `app`).

## Backing up data

It is really easy to backup data (you need to export the S3 config again):

```
restic -p /sec/pass -r s3:s3.server.tld/backups/app backup /path/to/app
```

And done, your data is backed up!

## Cleaning old backups

You can clean old backups easily with a single command:

```
restic -p /sec/pass -r s3:s3.server.tld/backups/app forget --keep-last 10 --prune
```

This command will only keep the 10 latest backups.

## Restoring a backup

To restore a backup, it's as easy as creating one:

```
restic -p /sec/app -r s3:s3.server.tld/backup/app restore latest --target /path/to/app
```

## The script

I use a small script on my servers:

```bash
#!/bin/bash

export AWS_ACCESS_KEY_ID=myaccesskey
export AWS_ACCESS_KEY_ID=iamverysecure

restic -p /sec/pass -r s3:s3.server.tld/backups/app forget --keep-last 10 --prune
restic -p /sec/app -r s3:s3.server.tld/backup/app restore latest --target /path/to/app
```
