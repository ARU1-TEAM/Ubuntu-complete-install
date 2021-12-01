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
  * [Window Theme](#window-theme)
  * [Icon Theme](#icon-theme)
  * [Cursor Theme](#cursor-theme)
  * [Fonts](#fonts)
  * [Panel Preferences](#panel-preferences)
* [Customize Terminal](#customize-terminal)
  * [](#
* [Install i3wm](#custom-i3wm)

## Introduction
This repository is made to help you in the complete installation of Ubuntu. At the end of this repo you will get a nice xfce4 fully nord customized on your ubuntu followed by I3WM and all it's customization as well
## Install Ubuntu
<p align="center"><img src="/screens/ubuntu.png" alt="ubuntu"></p>

### Create usb flash
 - Download [Ubuntu iso file](https://ubuntu.com/#download) and select the latest version.
 - Download [balenaEtcher](https://www.balena.io/etcher/).
 - Load balena etcher, put iso file and select your usb key.<p align="left"><img src="/screens/balena.png" alt="balena"></p>
### Boot on usb flash
 - Reboot your computer and press DEL key to get into your BIOS/UEFI.
 - Select your usb-key in the boot menu.
 - Save and exit.
### Follow Instructions
 - Select your language and click "Install Ubuntu".<p align="left"><img src="/screens/ubuntu_installation.png" alt="ubuntu_installation"></p>
 - Select your keyboard layout. <p align="left"><img src="/screens/keyboard_layout.png" alt="keyboard"></p>
 - Select "Minimal installation" and both of the "other options". <p align="left"><img src="/screens/minimal_installation.png" alt="minimal_installation"></p>
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
snap install spotify teams netflix-web vlc
sudo apt-get install flameshot gnome-calculator libreoffice
snap install code --classic
~~~

### Terminal applications
~~~ sh
sudo apt-get install cava htop ranger neofetch cmatrix nano vim hollywood sl
sudo add-apt-repository ppa:hsheth2/ppa
sudo apt-get install cava
~~~

### Install Xfce
### xubuntu-desktop
Install Xfce using this command
~~~ sh
sudo apt-get install xubuntu-desktop
~~~
Select lightdm to get vanilla Xfce <p align="left"><img src="/screens/configure_xfce_lightdm.png" alt="lightdm"></p>
Then run this command to enable lightdm, then you might reboot as well 
~~~ sh
sudo systemctl enable lightdm
~~~
### Uninstall Xfce
For uninstall Xfce using this command
~~~ sh
sudo apt-get purge xfce4 xfconf xfce4-utils xfwm4 xfce4-session xfdesktop4 exo-utils xfce4-panel xfce4-terminal  thunar gdm3
sudo apt autoremove
~~~
## Customize Xfce

### Window Theme
- First [download](https://www.gnome-look.org/p/1267246/) the nord theme.
- Create a ".themes" folder at your ~/
- Put the extracted file into the ".themes"
- Select the theme in both window manager and appearance settings like shown in the pictures
<p align="left"><img src="/screens/window_manager_style.png" alt="window_style"></p>
<p align="left"><img src="/screens/appearance_style.png " alt="appearance_style"></p>

### Icon Theme
Install Papirus Icon Theme
~~~ sh
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
~~~
Go into appearance settings and select papirus-dark. 
<p align="left"><img src="/screens/icon_theme.png" alt="icon_theme"></p>

### Cursor Theme
- First [download](https://www.pling.com/p/1505683/) the Lyrax theme.
- Create a ".icons" folder at your ~/
- Put the extracted file into the ".icons"
- Then go into "Mouse and Touchpad settings" over the "Theme" tab and select your cursor theme like so
<p align="left"><img src="/screens/cursor.png" alt="cursor"></p>

### Fonts
Install Cantarell font using 
~~~ sh
sudo apt-get install fonts-cantarell
~~~
Then you can select "Cantarell regular" in both window manager and appearance over the font tab

### Panel Preferences

<p align="left"><img src="/screens/panel_config.png" alt="panel-config"></p>
    
    
## Customize Terminal


