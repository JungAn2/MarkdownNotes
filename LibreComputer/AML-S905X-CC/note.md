> Just Note that never install their desktop version. It does not have hdmi driver installed

# Installation

[Libre OS Download](https://libre.computer/downloads/aml-s905x-cc/)

1. Flash the OS into the micro sd

    > Tools to use:
    > Windows:
    > - [Win32DiskImager](https://sourceforge.net/projects/win32diskimager/)
    > - Raspberry Pi Imager
    > Linux: [dd](https://man7.org/linux/man-pages/man1/dd.1.html) or [Gnome Disk Utility](https://wiki.gnome.org/Apps/Disks)
    > macOS: [Disk Utility](https://support.apple.com/guide/disk-utility/welcome/mac)

2. Insert sd card and boot
3. Done

## Installing GUI

[Instruction website](https://phoenixnap.com/kb/how-to-install-a-gui-on-ubuntu)
1. Update and upgrade repo
    ```
    Sudo apt update && apt upgrade
    ```
3. Install one of the display manager (GDM3 might be too heavy for libre.. Have not tried this library)
    > slim
    ```
    sudo apt install slim
    ```
    > LightDM
    ```
    sudo apt install lightdm
    ```
    
    3. Install one of the gui 
    > ubuntu desktop
    ```
    sudo apt install ubuntu-desktop
    ```
    > KDM Plasma (around 1.4GB)
    ```
    sudo apt install kde-plasma-desktop
    ```
    > XFCE
    ```
    sudo apt-get install xfce4-session xfce4-goodies
    ```
    > Mate
    ```
    sudo apt install ubuntu-mate-desktop
    ```
    > LXDE
    ```
    sudo apt install lxde
    ```
