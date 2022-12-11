---
title: "Void Linux"
date: 2022-12-11T20:17:28+07:00
draft: false
# weight: 1
# aliases: ["/first"]
tags: ["Voidlinux", "Linux"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
# description: "Desc Text."
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
# editPost:
#    URL: "https://github.com/ArchieTani/ArchieTani.github.io/content"
#    Text: "Suggest Changes" # edit text
#    appendFilePath: true # to append file path to Edit link
---

# Introduction to Void Linux

Void Linux is a lightweight, independent, rolling release operating system that is known for its simplicity and speed. It is a distribution that is built from scratch, without using any pre-existing codebase, which makes it unique in the world of Linux distributions.

## What sets Void Linux apart from other distributions?

One of the main differences between Void Linux and other Linux distributions is its package management system. While most distributions use a package manager like APT or Yum, Void Linux uses the XBPS (X Binary Package System) package manager. XBPS is a lightweight, easy-to-use package manager that is specifically designed for Void Linux.

Another key difference is that Void Linux is a rolling release distribution. This means that there are no major release versions and updates are continuously pushed to the repositories. This means that users always have access to the latest software and security updates without having to wait for a new release.

## Features of Void Linux

- Independent: Void Linux is developed and maintained by a team of volunteers and is not affiliated with any other Linux distribution or company. This means that it has full control over its development and can focus on building the best operating system possible.

- Rolling release: As mentioned earlier, Void Linux is a rolling release distribution. This means that users always have access to the latest software and security updates without having to wait for a new release.

- XBPS package manager: Void Linux uses the XBPS package manager, which is specifically designed for the distribution. It is a lightweight, easy-to-use package manager that makes it easy to install, update, and remove packages.

- Customizability: Void Linux allows users to customize their operating system by building their own packages or using the XBPS source packages repository (SBo). This allows users to tailor their operating system to their specific needs and preferences.

- Minimalistic: Void Linux is a minimalistic distribution that only includes the essential software and tools. This means that it has a small footprint and is fast and lightweight.

## Installing Void Linux

Installing Void Linux is relatively straightforward, but it does require some knowledge of the command line. The first step is to download the Void Linux ISO image from the official website. Once downloaded, the ISO image can be burned to a DVD or USB drive using a tool like Etcher.

Next, boot the computer from the DVD or USB drive and enter the live environment. Once in the live environment, open a terminal and run the following commands to begin the installation process:

```bash
fdisk /dev/sda 
n 
p 
1

+512M 
n 
p 
2

(default) 
w
```

This will create a new partition table on the hard drive and create two partitions - a 512MB boot partition and a root partition. The root partition will take up the remaining space on the hard drive.

Next, run the following commands to format the partitions and mount them:

```bash
mkfs.ext4 /dev/sda1 
mkfs.ext4 /dev/sda2 
mount /dev/sda2 /mnt 
mkdir /mnt/boot 
mount /dev/sda1 /mnt/boot
```

Now that the partitions are set up and mounted, the Void Linux installation can begin. Run the following command to install the base system:

```bash
xbps-install -S -R https://alpha.de.repo.voidlinux.org/current -r /mnt base-system
```

This will download and install the base system, which includes the kernel, basic tools, and libraries.

Once the base system is installed, it is necessary to configure the bootloader. Void Linux uses the GRUB bootloader, which can be installed by running the following command:

```bash
xbps-install -S grub
```

Next, edit the `/mnt/etc/default/grub` file and modify the `GRUB_CMDLINE_LINUX` line to include the `root` parameter, which specifies the root partition:

```bash
GRUB_CMDLINE_LINUX="root=/dev/sda2"
```

Finally, run the following commands to generate the GRUB configuration and install it to the boot partition:

```bash
grub-mkconfig -o /mnt/boot/grub/grub.cfg grub-install /dev/sda
```

With the bootloader installed and configured, the Void Linux installation is complete. Reboot the computer and remove the DVD or USB drive to boot into the newly installed Void Linux operating system.

## Using Void Linux

Once Void Linux is installed, users can start exploring the distribution and installing additional software. One of the first things to do is update the system by running the following command:

```bash
xbps-install -Suv
```

This will download and install the latest updates for the operating system and installed packages.

To install new software, users can use the `xbps-install` command followed by the package name. For example, to install the Firefox web browser, run the following command:

```bash
xbps-install firefox
```

The XBPS package manager also allows users to search for packages using the `xbps-query` command. For example, to search for packages containing the keyword "editor", run the following command:

```bash
xbps-query -Rs editor
```

Once a package is installed, it can be easily updated or removed using the `xbps-install` command with the `-u` or `-r` flags. For example, to update Firefox, run the following command:

```bash
xbps-install -u firefox
```

To remove Firefox, run the following command:

```bash
xbps-install -r firefox
```

In addition to using pre-built packages, Void Linux also allows users to build their own packages or use the XBPS source packages repository (SBo). This allows users to customize their operating system and tailor it to their specific needs and preferences.

## Conclusion

Void Linux is a unique and lightweight operating system that offers a simple, rolling release approach and a customizable package management system. Its independence and minimalistic design make it a great choice for users looking for a fast and efficient operating system. Whether you are a beginner or an experienced Linux user, Void Linux is worth considering for your next operating system.
