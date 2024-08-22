# Important!!!
There's an error: *can't mount /boot to start emergency mode*
And error: *[Dependency] Dependency faided for local file systems*

what I repair it:
- First check the reason of error, I read system log by `nvim`, because `journalctl -xb` can't roll up so I make it to an `.txt` by `journalctl -xb > ~/system-log.txt` then use `nvim ~/system-log.txt`.
- What I found is many `.zst` should locate in my linux core go nowhere and `/boot` is empty. So I knew I should mount the /boot again, reinstall some linux system file and remake the grub boot config.
- Then I enter USB Live, remount all of the disk partition.
```bash
mount /dev/nvme0n1pX /mnt
mount /dev/nvme0n1pX /mnt/boot
... (more disk)
``` 
- After mount, repair and check the system file, there're something need to choose.
```bash
fsck /dev/nvme0n1pX
fsck /dev/nvme0n1pX
...
```
- `pacman -Syu linux linux-firmware`
- `mkinitcpio -p linux`
- I don't know whether to reinstall GRUB but I did.
```bash
arch-chroot /mnt
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
grub-mkconfig -o /boot/grub/grub.cfg
```
- At last reboot and arch works!