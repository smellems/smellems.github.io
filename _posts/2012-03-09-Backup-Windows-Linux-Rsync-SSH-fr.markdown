---
layout: post
title: "Backup de Windows à Linux avec Rsync et SSH"
ref: backup
date: 2012-03-09 08:22
categories: b
lang: fr
---

Nous pouvons faire la sauvegarde des données sur le serveur d'entreprise vers un serveur de backup hors site. Avec Linux, nous utilisons Rsync pour transférer seulement les fichiers modifiés. Il existe plusieurs outils qui peuvent faire la même chose sur Windows. Le plus intéressant est cwRsync. Nous avons donc tous le nécessaire pour générer les clés publique/privée et exécuter Rsync à partir de Windows vers un serveur Linux.

## Environnement
### Serveur entreprise (Windows)
Les données que nous voulons sauvegarder sont sur une partition de ce serveur.

### Serveur backup (Debian Linux)
Ce serveur est exclusivement pour la sauvegarde et l'archivage des données de l'entreprise.

## Installation
### Sur Windows
- Installer cwRsync dans "C:\cwRsync".
- Ajouter "C:\cwRsync\bin" dans la variable PATH.
- Créer les répertoires "C:\cwRsync\home" et "C:\cwRsync\home\USER" (USER devrait être le nom de l'utilisateur qui exécutera le Rsync).
- Créer les clés publique/privée avec la commande suivante:
  - Les chemins "/home/USER/" correspondent aux répertoires que nous avons créer dans "C:\cwRsync\".
  - Laisser le mot de passe vide. 

`ssh-keygen -t rsa`

- Modifier les droits de la clé publique pour que le fichier ne soit pas visible à tous les utilisateurs.
- Transférer la clé publique sur le serveur de backup. 

### Sur Linux
- Installer openssh-server et rsync.
- Prévoir une partition pour les données (ex.: /media/backups/).
- Placer la clé publique dans le répertoire /home/USER/.ssh/ et renommer le fichier à authorized_keys 

### Sur Windows
- Tester la connexion sans mot de passe avec la commande suivante: 

`ssh USER@BackupServerIP`

- Tester le rsync: 

`rsync -v -rlt -z --delete "/cygdrive/D/" "USER@BackupServerIP:/media/backups/syncBackup/"`

- Créer un fichier bat avec la commande rsync et placer le dans C:\cwRsync\bin.
- Programmer l'exécution tous les jours à 0:30 (minuit et demi). 

### Sur Linux
Nous voulons archiver 2 semaines de données. Une fois par semaine, nous créons une archive avec tous les fichiers de l'entreprise. Tous les autres jours, l'archive contient juste les fichiers qui ont changer depuis la dernière archive.

- Créer le script à exécuter une fois par semaine (dimanche.sh) avec le contenu suivant:
  - Tar est utilisé pour créer une archive des données dans le répertoire syncBackup.
  - Ensuite les archives d'il y a trois semaines sont supprimées.

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

- Créer le le script à exécuter tous les autres jours (lundi-samedi.sh) avec le contenu suivant:
  - Tar est utilisé pour créer une archive des données dans le répertoire syncBackup.
  - Le numéro de la semaine est utilisé pour déterminer s'il faut créer une archive avec tous les fichiers. 

```
#!/bin/bash

/bin/tar -czpf /media/backups/`/bin/date +%F`.tar.gz -g /media/backups/`/bin/date +%U` /media/backups/syncBackup
```

- Programmer l'exécution des scripts tous les jours à 7:00, avec Crontab. 

```
# m h  dom mon dow   command

0 7 * * 0 /home/smellems/dimanche.sh
0 7 * * 1-6 /home/smellems/lundi-samedi.sh
```

- Installer No-IP... 

## Référence
- [Sync files from Windows to Linux using SSH](https://bluebill.wordpress.com/2011/05/04/sync-files-from-windows-to-linux-using-ssh/)
