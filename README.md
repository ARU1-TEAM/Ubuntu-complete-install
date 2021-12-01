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
* [Install Xfce](#install-xfce)
  * [xubuntu-desktop](#xubuntu-desktop)

## Install Ubuntu

### Create usb flash

 - Download [Ubuntu iso file](https://ubuntu.com/#download) and select the latest version.
 - Download [balenaEtcher](https://www.balena.io/etcher/).
 - Load balena etcher, put iso file and select your usb key.
### Boot on usb flash
 - Reboot your computer and press DEL key to get into your BIOS/UEFI.
 - Select your usb-key in the boot menu.
 - Save and exit.
### Follow Instructions
 - Select your language and click "Install Ubuntu".
 - Select your keyboard layout.
 - Select "Minimal installation" and both of the "other options".
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
sudo apt-get install curl git zsh wget nano vim zip gparted build-essential locate snap xarchiver
~~~
Install oh-my-zsh
~~~
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
~~~
If you need nvidia, install these
~~~ sh
sudo apt-get install nvidia nvidia-utils nvidia-settings
~~~

### Side applications
Install Visual Studio Code
~~~ sh
snap install spotify code --classic
~~~

### Install Xfce

### xubuntu-desktop
