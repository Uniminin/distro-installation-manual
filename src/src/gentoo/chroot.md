## Chrooting into Gentoo
- Create directory `repos.conf` if does not exist: `<superuser> mkdir --parents /mnt/gentoo/etc/portage/repos.conf`.
- Copy the Gentoo repository configuration file provided by Portage to the `repos.conf` directory: `<superuser> cp /mnt/gentoo/usr/share/portage/config/repos.conf /mnt/gentoo/etc/portage/repos.conf/gentoo.conf`.
- Copy DNS info: `cp /etc/resolv.conf /mnt/gentoo/etc/`.
- Mounting the necessary filesystems for chrooting:
```
<superuser> mount --types proc /proc /mnt/gentoo/proc
<superuser> mount --rbind /sys /mnt/gentoo/sys
<superuser> mount --rbind /dev /mnt/gentoo/dev
```
- Chroot into gentoo: `<superuser> chroot /mnt/gentoo /bin/bash`.
- Reload the settings of `/etc/profile` in memory: `source /etc/profile`.
- Mount Boot partition: `<superuser> mount /dev/sdx2 /boot/`.