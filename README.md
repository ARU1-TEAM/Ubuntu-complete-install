## Table of contents

* [Introduction](#introduction)
* [Install Ubuntu](#install-ubuntu)
  * [Create usb flash](#create-usb-flash)
  * [Boot on usb flash](#boot-on-usb-flash)
  * [Follow Instructions](#follow-instructions)
  * [Install grub-bootloader](#install-grub-bootloader)
* [Install packages](#install-packages)
  * [Primary packages](#primary-packages)
  * [Side applications](#side-applications)
  * [Terminal applications](#terminal-applications)
* [Install Xfce](#install-xfce)
  * [Xubuntu-desktop](#xubuntu-desktop)
  * [Uninstall Xfce](#uninstall-xfce)
* [Customize Xfce](#customize-xfce)
  * [Window Manager settings](#window-manager-settings)
  * [Appearance settings](#appearance-settings)
  * [Pannel preferences](#pannel-preferences)
* [Install i3wm](#custom-i3wm)

## Introduction
This repository is made to help you in the complete installation of Ubuntu.
## Install Ubuntu

### Create usb flash
 - Download [Ubuntu iso file](https://ubuntu.com/#download){:target="_blank" rel="noopener"} and select the latest version.
 - Download [balenaEtcher](https://www.balena.io/etcher/){:target="_blank"}.
 - Load balena etcher, put iso file and select your usb key.<p align="center"><img src="/screens/balena.png" alt="balena"></p>
### Boot on usb flash
 - Reboot your computer and press DEL key to get into your BIOS/UEFI.
 - Select your usb-key in the boot menu.
 - Save and exit.
### Follow Instructions
 - Select your language and click "Install Ubuntu".<p align="center"><img src="/screens/ubuntu_installation.png" alt="ubuntu_installation"></p>
 - Select your keyboard layout. <p align="center"><img src="/screens/keyboard_layout.png" alt="keyboard"></p>
 - Select "Minimal installation" and both of the "other options". <p align="center"><img src="/screens/minimal_installation.png" alt="minimal_installation"></p>
 - Select "Erase disk and install Ubuntu" (be carful, this option only works if you want to install the os on an empty disk , otherwise select the other option).
 - Select your regiion
 - Choose your name, computer's name, username and password.
 - Once the installation is finished, restart your computer.

### Install grub-bootloader

Install os-prober and grub2 packages 
~~~ sh
sudo apt-get install os-prober grub2
~~~
Start os-prober
~~~ sh
sudo os-prober
~~~
Update grub
~~~ sh
sudo update-grub
~~~

## Install packages

### Primary packages
Update your packages
~~~ sh
sudo apt-get update
~~~
Install all the needed packages
~~~ sh
sudo apt-get install curl git zsh wget nano vim zip gparted build-essential locate snap xarchiver gdebi
~~~
Install oh-my-zsh
~~~
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
~~~
If you need nvidia, install these
~~~ sh
sudo apt-get install nvidia-settings
~~~

### Side applications
Install the user graphical applications 
~~~ sh
snap install spotify teams netflix-web vlc;
sudo apt-get install flameshot gnome-calculator libreoffice;
snap install code --classic
~~~

### Terminal applications
~~~ sh
sudo apt-get install cava htop ranger neofetch cmatrix nano vim hollywood sl;
sudo add-apt-repository ppa:hsheth2/ppa;
sudo apt-get install cava
~~~

### Install Xfce
### xubuntu-desktop
Install Xfce using this command
~~~ sh
sudo apt-get install xubuntu-desktop;
sudo systemctl enable lightdm
~~~
Select lightdm to get vanilla Xfce <p align="left"><img src="/screens/configure_xfce_lightdm.png" alt="lightdm"></p>
### Uninstall Xfce
For uninstall Xfce using this command
~~~ sh
sudo apt-get purge xfce4 xfconf xfce4-utils xfwm4 xfce4-session xfdesktop4 exo-utils xfce4-panel xfce4-terminal  thunar gdm3;
sudo apt autoremove
~~~
## Customize Xfce

### Window Manager settings
- First we will [download](https://www.gnome-look.org/p/1267246/){:target="_blank"} the nord theme.
- First we will<a href="https://www.gnome-look.org/p/1267246/" target="_blank">download</a> the nord theme.



