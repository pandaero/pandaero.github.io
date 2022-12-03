---
title: "Dual Boot Windows and Linux (with Secure Boot)"
date: 2022-12-3
---
I just got a new computer, and with it, a new chance to set up the operating system(s) the way I want to. I think it is an initiation ritual for any coder/programmer to install a working Linux distribution. This ritual, depending on the choices made, can be very hard, or very smooth. I chose a harder path. It is not my first rodeo, and still it has been a long, difficult process. This is:
- Dual-boot Windows and Linux (Debian)
- rEFInd as the boot manager
- Secure Boot kept on

So far, I have only managed to install Debian, but had no luck with rEFInd (while leaving Secure Boot on). The device is a Microsoft Surface Book 2.

This process is also a reminder of the portability of data in computers. Consider for example having to migrate a huge library of music or photos. Also, package managers and a familiar web browser are the first tools to install. I use [scoop](https://scoop.sh) with Windows to install almost every program I need. A password manager such as [Bitwarden](https://bitwarden.com/), and browsers with accounts such as [Chrome](https://www.google.com/chrome) and [Firefox](https://www.mozilla.org/firefox) go a long way towards getting set-up quickly on a new device.

Steps
- Partition for Linux (easy)
    - Windows Disk Management
        - Shrink the destination volume (this leaves free space available for another OS)
- Installing Debian (medium)
    - Make live installation device
        - Install [Rufus](https://rufus.ie) and get the [image from Debian](https://www.debian.org/CD/live/)
    - Get specific network adapter firmware
        - In the case of the Surface Book 2, this was a [package](https://debian.pkgs.org/11/debian-nonfree-amd64/firmware-libertas_20210315-3_all.deb.html).
    - Boot on live device
        - Set this up via UEFI or find a special button combination (Surface Book 2: Volume down while starting up)
    - Follow the Debian installer.
    - Install network adapter using `apt` from deb package
        - To install packages directly with `apt` (from files): `sudo apt install ./<deb file>`.
    - Reboot
    - Setting up device firmware ([linux-surface](https://github.com/linux-surface/linux-surface))
        - Mostly using `apt`

At this point, I had spent countless hours trying to install, uninstall, reinstall rEFInd, and rebooting the device to see if things were working. Needless to say, this is still a challenge, though it is a nice-to-have, rather than a need-to-have.

- Setting up Debian (medium)
    - Login manager theme SDDM
        - With LXQt as the Desktop Environment, the setup is very basic. This is not particularly pretty, but it is light and familiar.
        - I came across this [theme](https://github.com/MarianArlt/sddm-sugar-dark) that I found suitable.
        - Great wallpaper images can be found in the [Wikimedia Commons](https://commons.wikimedia.org/wiki/Main_Page)

- Installing rEFInd (hard)
