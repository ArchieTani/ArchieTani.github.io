---
title: "Arch Install (Minimal)"
date: 2022-12-11T14:04:33+07:00
# weight: 1
# aliases: ["/first"]
tags: ["archlinux"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: ""
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
---

# How to Install ArchLinux

ArchLinux is a Linux-based operating system that uses the KISS (Keep It Simple, Stupid) principle. This makes ArchLinux easy to use for users who want to customize their operating system according to their needs.

Here are the steps for installing ArchLinux:

## Preparation

1. Download the ArchLinux ISO from [its site](https://www.archlinux.org/download/).
2. Create a bootable USB or CD/DVD using the ISO.
3. Make sure your computer is connected to the internet.

## Install

1. Boot from the USB or CD/DVD that you have created.
2. Choose the language you want.
3. Select the option "Boot Arch Linux (x86_64)" for a 64-bit system or "Boot Arch Linux (i686)" for a 32-bit system.
4. After entering the command line, run the command `loadkeys <keyboard_name>` to set the keyboard according to your needs.
5. Next, run the command `ping -c 3 google.com` to make sure your internet connection is working properly.
6. If the internet connection is connected, run the command `timedatectl set-ntp true` to set the time and date.
7. Next, partition the hard drive with the command `fdisk -l` to see the available partitions, then select the partition you want to use and run the command `mkfs.ext4 /dev/sdX` to create a new partition.
8. Create a folder `arch` on the partition that has been created, then mount the partition to the `arch` folder with the command `mount /dev/sdX /mnt/arch`.
9. Install the ArchLinux base system with the command `pacstrap /mnt base base-devel`.
10. Generate fstab with the command `genfstab -U /mnt >> /mnt/etc/fstab`.
11. Enter the installed system with the command `arch-chroot /mnt`.
12. After entering the system, run the command `ln -sf /usr/share/zoneinfo/Region/City /etc/localtime` to set the time zone according to your location.
13. Then run the command `hwclock --systohc` to set the hardware time.
14. Create a hostname with the command `echo hostname_name > /etc/hostname`.
15. Edit the file `/etc/hosts` and add the hostname at the end of the line that contains the loopback address (`127.0.0.1`).
16. Set the root password with the command `passwd`.
17. Install a bootloader, such as Grub, with the command `pacman -S grub && grub-install /dev/sdX && grub-mkconfig -o /boot/grub/grub.cfg`.
18. Finally, exit the chroot environment with the command `exit` and reboot the system with the command `reboot`.

Congratulations, you have successfully installed ArchLinux!
