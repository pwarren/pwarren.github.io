---
title: "EFI single boot on a MacBook Air"
tags: open-source tech
description: "How I got my MacBook air to single boot Debian"
---

EFI needs its own smallish partition with a fat32 filesystem

here's my layout with just one disk:

       (parted) print
       Model: ATA Hitachi HTS54503 (scsi)
       Disk /dev/sda: 320GB
       Sector size (logical/physical): 512B/512B
       Partition Table: gpt
       
       Number Start End Size File system Name Flags
       1 1049kB 512MB 511MB fat32 boot
       2 512MB 316GB 316GB ext4
       3 316GB 320GB 4023MB linux-swap(v1)

Now, debian does sort of support UEFI booting with the 7.2 install discs (haven't tried 7.3 yet but should be good), but there was some extra mucking about I had to do.

Once you've installed, and it boots the flashing folder icon (or question mark, I forget which). Boot into rescue mode, and let debian find the right root partition, and execute a shell in that partition.

You may have to:

`mount /boot/efi`

then:

`apt-get install grub-efi-amd64`

Now we're almost there! the installer for grub-efi-amd64 puts the boot file in /efi/EFI/debian/grub64x64.efi

And we need to put that in the right place for EFI to load it properly:

`mkdir /boot/efi/EFI/boot
cp /boot/efi/EFI/debian/grubx64.efi /boot/efi/EFI/boot/bootx64.efi`

then run:

`update-grub`

To make sure all the configs are in the right place.

Then reboot! and you should eventually get into debian :)

If you have a white screen for ~30s after the boot chime, and you want to get rid of the wait, you'll have to boot an OS X disk and run:

`bless --device /dev/disk0s1 --setBoot --verbose`

substituting the proper device node for your boot device of course.