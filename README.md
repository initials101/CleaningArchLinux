# Arch Linux System Maintenance and Cleanup

This document outlines essential commands and best practices for maintaining a clean and efficient Arch Linux system. Regular cleanup helps free disk space, remove unnecessary files, and optimize system performance.

---

## Package Cache Management

Arch Linux stores downloaded package files in the package cache located at `/var/cache/pacman/pkg/`. Over time, this cache can grow significantly.

- **Remove old cached packages while retaining the latest installed versions:**

  ```bash
  sudo paccache -r

    Remove all cached packages (use with caution):

    bash

    sudo paccache -ruk0

Orphaned Package Removal

Orphaned packages are dependencies that are no longer required by any installed package. Removing them helps reduce clutter:

bash

sudo pacman -Rns $(pacman -Qtdq)

Systemd Journal Log Cleanup

Systemd journal logs can accumulate and consume considerable disk space. Manage logs effectively with the following commands:

    Limit journal size to 100MB:

    bash

sudo journalctl --vacuum-size=100M

Remove journal logs older than 2 weeks:

bash

    sudo journalctl --vacuum-time=2weeks

User Cache Cleanup

User applications often store cache files in the ~/.cache directory. Clearing this cache can free up space:

bash

rm -rf ~/.cache/*

Alternatively, consider using system cleaning tools such as bleachbit for a safer and more comprehensive cleanup.
Additional Recommendations

    Review and remove unused configuration files.
    Remove old or unused kernel versions to free space.
    Always ensure you have recent backups before performing system cleanup operations.

Note: Execute these commands with caution. Improper use may affect system stability or remove important data.

Maintaining a clean system contributes to better performance and efficient resource usage. Regularly schedule cleanup tasks as part of your system maintenance routine.
