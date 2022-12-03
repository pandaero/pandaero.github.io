---
title: "Dual Boot Windows and Linux (with Secure Boot)"
date: 2022-12-3
---
I think it is an initiation ritual for any coder/programmer to install a working Linux distribution. This ritual, depending on the choices made, can be very hard, or very smooth. I chose a harder path. It is not my first rodeo, but I just got a new computer, and with it, a new chance to set up the operating system(s) the way I want to. This is:
- Dual-boot Windows and Linux (Debian)
- rEFInd as the boot manager
- Secure Boot kept on

Steps
- Partition for Linux (easy)
- Installing Debian (medium)
    - make liveusb
    - get specific network adapter firmware
    - install adapter using apt from deb package
    - reboot
    - working with internet
    - setting up device firmware (surface)
- Installing rEFInd (hard)
    - lsblk to check partitions
    - mount EFI partition sudo mount /dev/sda /mnt
    - install shim (build and sign) / from package
    - get latest refind zip
    - sign refind 
- Setting up Debian (medium)
    - Login manager theme SDDM
    - screensaver
    - appearance

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, World!");
    return (0);
}
```
A little code to say hello.