# btrfs-du
Print BTRFS snapshots disk usage

This project is inspired by https://github.com/nachoparker/btrfs-du however it stopped working on my machien after updating the kernel from v6.9.14 to v6.12.22, therefore I made my own.

This does NOT require quotas to be enabled.

Only works for read only volumes (hence snapshots)

# Usage

```
Usage: /usr/local/sbin/btrfs-snapshots-du [-s name|ref|exc|id] <btrfs-root-directory>

  -s, --sort-by   sort key: name (default), ref (Usage referenced),
                  exc (Usage exclusive), or id (Subvolume ID)
```

## Example Output

```
$ btrfs-du /singularitaettssauerkraut2/media

ID     Name                  Usage referenced  Usage exclusive
--------------------------------------------------------------
5054   photos.20240602       3.64TiB           13.16GiB
16400  photos.20240707       3.69TiB           442.54MiB
16781  photos.20240804       3.68TiB           353.20MiB
22492  photos.20240901       3.53TiB           4.26GiB
22731  photos.20241006       3.55TiB           331.64MiB
22991  photos.20241103       3.58TiB           119.08MiB
23274  photos.20241201       3.64TiB           9.87GiB
24195  photos.20250105       3.62TiB           8.26GiB
25255  photos.20250310       3.56TiB           8.02GiB
25739  photos.20250406       3.59TiB           7.05GiB
25809  photos.20250413       3.54TiB           3.09MiB
25879  photos.20250420       3.63TiB           7.56MiB
25949  photos.20250427       3.61TiB           46.69MiB
26104  photos.20250504       3.84TiB           336.00KiB
26261  photos.20250506       3.84TiB           304.00KiB
26402  photos.20250507       3.84TiB           304.00KiB
26412  photos.20250513T1011  3.84TiB           7.38GiB
--------------------------------------------------------------
       Total                                   59.27GiB
```

