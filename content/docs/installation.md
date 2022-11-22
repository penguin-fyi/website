---
title: "Installation"
date: 2021-01-22T21:24:44-06:00
summary: "Instructions for installing PENGUIN"
showDate: false
showAuthor: false
showSummary: true
showReadingTime: true
showPagination: false
draft: false
---

There are currently several ways to install the PENGUIN Desktop Environment.

## New Install (manual)
Installing **PENGUIN** during a manual Arch Linux installation is the most straight-forward, and therefore most recommended, method. We will not cover the entire Arch Linux install; can read more about that [here](https://wiki.archlinux.org/title/Installation_guide).

1. Follow Arch install guide up to ***Select the mirrors***

2. After selecting mirrors, add the **PENGUIN** mirrorlist, by creating `/etc/pacman.d/mirrorlist-penguin`
```
Server = https://repo.penguin.fyi/packages/$repo/$arch
SigLevel = Optional TrustAll

```

3. Add mirrorlist to `/etc/pacman.conf`
```
[penguin]
Include = /etc/pacman.d/mirrorlist-penguin

```

4. Install the complete PENGUIN Desktop Environment
```
pacstrap /mnt penguin-base penguin-desktop

```

5. Continue Arch installation as usual


## New Install (archinstall)
Installing **PENGUIN** during Arch installation via `archinstall` is also possible. This method is two part: `archinstall` and `arch-chroot`

1. **archinstall**  
  In this part of the installation, you may setup your system as needed, but the following points are required.
  
    - Do not create **User account**; this will be done later
    - For **Profile**; choose **minimal**
    - For **Audio**; choose **pipewire**
    - For **Network configuration**; choose **NetworkManager**
  
    When the installation is complete, select **Yes** to enter `chroot`

2. **arch-chroot**  
  After completing steps 1 and 2 below, you may remain in the `chroot` for any additional setup to your new system.

    1. Run setup script to add mirrorlist and install 
    ```
    curl https://repo.penguin.fyi/setup_mini.sh | sh
    
    ```
    
    2. Add user account
    ```
    useradd -m username
    passwd username
    
    ```

    3. Exit `chroot` with `Ctrl+D` and reboot to new system

## Existing Install [unsupported]

*Coming Soon!*

## PKGBUILD Install [unsupported]

*Coming Soon!*


