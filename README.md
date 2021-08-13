### pihole_sync

#### Sync gravity database
- Syncs pihole data to two or more hosts by backing up the gravity DB and restoring it on the other hosts.

#### Sync local DNS
- Pushes out local DNS records via /etc/pihole/custom.list.
- These lists can be unique per server or all the same as it uses inventory_hostname as the source file.
- Maintain a master and use symlinks to keey them all the same or use unique files to keep them all unique.

```
dr@admin:sync $ ls -l
total 12
drwxr-xr-x 2 dr dr 4096 Aug 13 12:09 backup
-rw-r--r-- 1 dr dr 1461 Aug 13 12:09 local-dns
lrwxrwxrwx 1 dr dr    3 Aug 12 21:34 ph-mgmt -> ph1
lrwxrwxrwx 1 dr dr    9 Aug 13 10:44 ph1 -> local-dns
lrwxrwxrwx 1 dr dr    3 Aug 11 15:37 ph2 -> ph1
-rwx------ 1 dr dr 1909 Aug 13 12:08 sync.yaml
```

```
dr@admin: $ cat ansible.inventory
[pihole]
ph1
ph2
ph-mgmt
```
