# CleaningArchLinux

markdown

# Arch Linux System Cleaning Guide

This guide provides common commands and tips to clean and maintain your Arch Linux system by freeing up disk space and removing unnecessary files.

## Clear Package Cache

Arch Linux caches installed packages in `/var/cache/pacman/pkg/`. To remove old cached packages but keep the latest installed versions, run:

```bash
sudo paccache -r

To remove all cached packages (use with caution):

bash

sudo paccache -ruk0

Remove Orphaned Packages

Orphaned packages are dependencies no longer required by any installed package. Remove them with:

bash

sudo pacman -Rns $(pacman -Qtdq)

Clean Systemd Journal Logs

Systemd journal logs can consume significant disk space. To limit their size to 100MB:

bash

sudo journalctl --vacuum-size=100M

To remove logs older than 2 weeks:

bash

sudo journalctl --vacuum-time=2weeks

Clear User Cache

User applications store cache files in ~/.cache. You can clean this directory manually or use tools like bleachbit.

bash

rm -rf ~/.cache/*

Additional Tips

    Remove unused configuration files.
    Remove old kernels if multiple versions are installed.

Use these commands carefully and ensure you have backups if necessary.



