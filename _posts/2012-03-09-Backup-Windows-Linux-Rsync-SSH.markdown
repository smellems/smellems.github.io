---
layout: post
title: "Backup from Windows to Linux with Rsync and SSH"
ref: backup
date: 2012-03-09 08:22
categories: b
lang: en
---

We can backup data from the enterprise server to a backup server offsite. With Linux, we use Rsync to transfer only modified files. There are several tools that can do the same on Windows. The most interesting is cwRsync. So we have everything needed to generate public/private keys and run Rsync from Windows to a Linux server.

## Environment
### Enterprise server (Windows)
The data we want to backup is on a partition on this server.

### Backup server (Debian Linux)
This server is only for backup and archiving business data.

## Installation
### On Windows

- Install cwRsync in "C:\cwRsync".
- Add "C:\cwRsync\bin" to PATH.
- Create the directory "C:\cwRsync\home" and "C:\cwRsync\home\USER" (USER should be the name of the user who will run the Rsync).
- Create public/private keys with the following command:
  - Paths with "/home/USER/" correspond to the directories that we created in "C:\cwRsync\".
  - Leave the password blank. 

`ssh-keygen -t rsa`

- Modify the rights of the public key file so that it is not visible to all users.
- Transfer the public key on the backup server. 

### On Linux
- Install openssh-server and rsync.
- Provide data to a partition (ex.: /media/backups/).
- Place the public key in /home/USER/.ssh/ and rename the file to authorized_keys. 

## On Windows
- Test the connection without a password with the following command: 

`ssh USER@BackupServerIP`

- Test Rsync: 

`rsync -v -rlt -z --delete "/cygdrive/D/" "USER@BackupServerIP:/media/backups/syncBackup/"`

- Create a bat file with the rsync command and place it in C:\cwRsync\bin.
- Schedule execution every day at 0:30 (half past midnight). 

### On Linux
We want to archive data for 2 weeks. Once a week, we are creating an archive with all files. All other days, the archive contains only the files that have changed since the last archive.

- Create the script to run once a week (sunday.sh) with the following contents:
  - Tar is used to create a data archive in the directory syncBackup.
  - Archives from three weeks ago are deleted. 

```
#!/bin/bash

/bin/tar -czpf /media/backups/`/bin/date +%F`_full.tar.gz -g /media/backups/`/bin/date +%U`x /media/backups/syncBackup

/bin/rm -rf /media/backups/`/bin/date --date="21 days ago" +%U`
/bin/rm -rf /media/backups/`/bin/date --date="21 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="20 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="19 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="18 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="17 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="16 days ago" +%F`.tar.gz
/bin/rm -rf /media/backups/`/bin/date --date="15 days ago" +%F`.tar.gz
```

- Create the script to run every other day (monday-saterday.sh) with the following contents:
  - Tar is used to create a data archive in the directory syncBackup.
  - The week number is used to determine whether to create an archive with all files. 

```
#!/bin/bash

/bin/tar -czpf /media/backups/`/bin/date +%F`.tar.gz -g /media/backups/`/bin/date +%U` /media/backups/syncBackup
```

- Schedule scripts to run every day at 7:00, with Crontab. 

```
# m h  dom mon dow   command

0 7 * * 0 /home/joe/dimanche.sh
0 7 * * 1-6 /home/joe/lundi-samedi.sh
```

- Install No-IP... 

## Reference
- [Sync files from Windows to Linux using SSH](https://bluebill.wordpress.com/2011/05/04/sync-files-from-windows-to-linux-using-ssh/)
