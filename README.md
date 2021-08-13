### pihole_sync

#### Sync gravity database
- Syncs pihole data to two or more hosts by backing up the gravity DB and restoring it on the other hosts.

#### Sync local DNS
- Pushes out local DNS records via /etc/pihole/custom.list.
- These lists can be unique per server or all the same as it uses inventory_hostname as the source file.
- Maintain a master and use symlinks or keep them all unique.
