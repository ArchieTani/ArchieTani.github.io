---
title: "Arch Install Using Archinstaller"
date: 2022-12-11T14:23:45+07:00
# weight: 1
# aliases: ["/first"]
tags: ["archlinux"]
# categories: ["Linux"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: true
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
    image: "arch.png" # image path/url
    responsiveImages: true
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
editPost:
    URL: ""
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
---

## How to Install Arch Linux Using Archinstaller

Arch Linux is a popular, lightweight and flexible Linux distribution that is known for its simplicity and customization. It is suitable for users who want to have full control over their system and want to build it from scratch.

Installing Arch Linux can be a daunting task for beginners, especially if you are not familiar with the command line. But don't worry, there is a tool called Archinstaller that makes the process much easier and faster.

In this article, we will show you how to install Arch Linux using Archinstaller. We will also discuss some of the key features of Archinstaller and how to use it to customize your system.

### What is Archinstaller?

Archinstaller is a graphical tool for installing Arch Linux. It is based on the Archiso project and uses the same installation process as the official Arch Linux installation media.

The main advantage of using Archinstaller is that it provides a user-friendly interface that guides you through the installation process. It also allows you to customize your system by selecting the packages, desktop environment and other options.

### Requirements

Before you start the installation, you need to make sure that your system meets the following requirements:

- A computer or virtual machine with at least 512MB of RAM and 2GB of free disk space.
- A bootable USB drive or DVD with the Arch Linux installation media.
- An active internet connection.

### Step 1: Download Archinstaller

To download Archinstaller, visit the official website and click on the "Download" button. You will be redirected to the download page where you can choose the latest version of Archinstaller.

At the time of writing, the latest version is Archinstaller 1.1.0. It is available in two formats: a Live ISO image and a netinstall image.

The Live ISO image contains a complete Arch Linux system that you can boot and use to install Arch Linux. The netinstall image is a smaller version that downloads the latest packages from the internet during the installation.

For this tutorial, we will use the Live ISO image. Download the ISO image and save it on your computer.

### Step 2: Create a Bootable USB Drive

Next, you need to create a bootable USB drive with the Arch Linux installation media. You can use any tool that can create a bootable USB drive, such as Etcher, Rufus or UNetbootin.

Insert a USB drive into your computer and open the tool that you have chosen. Select the ISO image that you have downloaded in the previous step and click on the "Burn" or "Create" button to start the process.

Once the process is completed, you can safely remove the USB drive from your computer.

### Step 3: Boot from the USB Drive

Now, you need to boot your computer from the USB drive that you have just created. To do this, you need to change the boot order in the BIOS or UEFI settings.

The exact steps to do this vary depending on your computer's manufacturer and model. In general, you need to press a key (such as F2, F10 or Esc) during the boot process to enter the BIOS or UEFI settings.

Once you are in the BIOS or UEFI settings, navigate to the "Boot" or "Startup" tab and look for the option to change the boot order. Select the USB drive as the first boot device and save the changes.

Restart your computer and it should boot from the USB drive. You will see the Arch Linux boot menu where you can selectthe "Arch Linux archinstaller" option to start the installation process.

### Step 4: Select the Language and Keyboard Layout

When you start Archinstaller, you will be prompted to select the language and keyboard layout for the installation process. Use the arrows keys to navigate and press Enter to select the options that you want.

### Step 5: Connect to the Internet

Archinstaller needs an active internet connection to download the latest packages and updates during the installation. You can connect to the internet using a wired or wireless network.

If you are using a wired network, plug in the Ethernet cable and Archinstaller will automatically detect and connect to the network.

If you are using a wireless network, press the Tab key to switch to the terminal window and type the following command to list the available wireless networks:

```bash
# wifi-menu
```

A list of available networks will be displayed. Use the arrows keys to select the network that you want to connect to and press Enter. Enter the password for the network when prompted and press Enter again to connect.

### Step 6: Set the Time and Date

Next, you need to set the time and date for your system. Archinstaller will automatically detect your location and set the time zone based on it. However, you can also manually select the time zone by pressing the Tab key to switch to the terminal window and typing the following command:

```bash
# timedatectl set-timezone <zone>
```

Replace `<zone>` with the time zone that you want to use. For example, to set the time zone to New York, you can use the following command:

```bash
# timedatectl set-timezone America/New_York
```

To set the date and time, use the following command:

```bash
# date --set="YYYY-MM-DD HH:MM:SS"
```

Replace `YYYY-MM-DD HH:MM:SS` with the date and time that you want to use. For example, to set the date and time to January 1, 2021 at 12:00:00, you can use the following command:

```bash
# date --set="2021-01-01 12:00:00"
```

### Step 7: Partition the Disk

Before you can install Arch Linux, you need to partition the disk where you want to install it. Archinstaller provides two options for partitioning the disk: automatic and manual.

#### Automatic Partitioning

The automatic partitioning option is recommended for beginners. It will automatically create the partitions and format them with the default settings.

To use the automatic partitioning option, select the disk that you want to partition and press Enter. Archinstaller will show you a summary of the partitions that will be created. If you are satisfied with the settings, press Enter to continue.

#### Manual Partitioning

The manual partitioning option allows you to customize the partitions and the filesystems. It is recommended for advanced users who want to have more control over the installation process.

To use the manual partitioning option, select the disk that you want to partition and press Enter. You will be prompted to choose the partitioning tool that you want to use. You can choose between cfdisk, fdisk and parted.

Once you have selected the partitioning tool, use it to create the partitions that you want. Make sure to create at least two partitions: one for the root (/) filesystem and one for the boot (/boot) filesystem.

After you have created the partitions, you need to format them with the filesystem that you want to use. Arch Linux supports a variety of filesystems, such as ext4, xfs and btrfs.

To format a partition with a filesystem, use the following command:

```bash
# mkfs.<filesystem> <partition>
```

Replace `<filesystem>` with the filesystem that you want to use (for example, ext4) and `<partition>` with the partition that you want to format (for example, /dev/sda1).

For example, to format the root partition with the ext4 filesystem, you can use the following command:

```bash
# mkfs.ext4 /dev/sdaX
```

### Step 8: Install the Base System

Once you have partitioned the disk, you can start installing the base system. Archinstaller will automatically download and install the latest packages and updates from the internet.

To start the installation, press Enter on the `Install` screen. You will be prompted to select the packages that you want to install. The default package selection is recommended for most users.

If you want to customize the package selection, you can use the arrow keys to navigate and the Space key to select or deselect the packages.

Once you have selected the packages that you want, press Enter to start the installation. Archinstaller will show you a summary of the packages that will be installed and the disk space that will be used. If you are satisfied with the settings, press Enter to continue.

The installation process may take some time, depending on your internet connection and the packages that you have selected.

### Step 9: Configure the System

After the base system is installed, you need to configure the system settings. Archinstaller will prompt you to set the hostname, root password and time zone.

- The hostname is the name of your computer. You can use any name that you want, but it is recommended to use a descriptive and unique name.
- The root password is the password for the root user. This is the most powerful user in the system and you should choose a strong and secure password.
- The time zone is the time zone where you are located. Archinstaller will automatically detect your location and set the time zone based on it. However, you can also manually select the time zone from the list.

After you have set the hostname, root password and time zone, press Enter to continue.

### Step 10: Install the Bootloader

The bootloader is the software that is responsible for booting the operating system. Arch Linux uses the GRUB bootloader by default.

To install the GRUB bootloader, select the disk where you want to install it and press Enter. Archinstaller will automatically detect the partitions and install the bootloader on the boot partition.

If you want to customize the bootloader settings, you can press the Tab key to switch to the terminal window and edit the /etc/default/grub file.

After the bootloader is installed, press Enter to continue.

### Step 11: Reboot the System

Once the installation is completed, you need to reboot the system to boot into the newly installed Arch Linux. Press Enter on the "Reboot" screen to restart the system.

When the system is restarted, remove the USB drive and boot from the hard drive. You will see the GRUB boot menu where you can select the "Arch Linux" option to boot into Arch Linux.

### Step 12: Login and Update the System

After the system is booted, you will be prompted to login. Enter the root username and the password that you have set during the installation.

Once you are logged in, you should update the system to get the latest packages and security updates. To update the system, use the following command:

```bash
# pacman -Syu
```

The `pacman` command is the package manager for Arch Linux. The `-S` flag installs the packages and the `-y` flag updates the database. The `-u` flag upgrades the installed packages to their latest versions.

The update process may take some time, depending on the number of packages that need to be updated.

### Step 13: Install a Desktop Environment

Arch Linux is a minimalistic distribution that does not come with a pre-installed desktop environment. If you want to use a graphical user interface, you need to install a desktop environment.

There are many desktop environments available for Arch Linux, such as GNOME, KDE, Xfce and LXDE. You can choose the one that you like the most and install it using the `pacman` command.

For example, to install the GNOME desktop environment, you can use the following command:

```bash
# pacman -S gnome
```

After the desktop environment is installed, you need to enable the display manager. The display manager is the software that is responsible for starting the desktop environment.

To enable the display manager, use the following command:

```bash
# systemctl enable gdm
```

Replace `gdm` with the name of the display manager that you want to use. For example, to use the LightDM display manager, you can use the following command:

```bash
# systemctl enable lightdm
```

After the display manager is enabled, restart the system to start the desktop environment. You will see the login screen where you can enter your username and password to login.

### Conclusion

In this article, we have shown you how to install Arch Linux using Archinstaller. We have also discussed some of the key features of Archinstaller and how to use it to customize your system.

Installing Arch Linux can be a challenging task, especially for beginners. But with Archinstaller, the process becomes much easier and faster.

We hope that this tutorial has been helpful and you have successfully installed Arch Linux on your system. If you have any questions or feedback, feel free to leave a comment below.
