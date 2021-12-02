## Table of Contents

* [Introduction](#introduction)
* [Install Ubuntu](#install-ubuntu)
  * [Create USB Flash](#create-usb-flash)
  * [Boot On USB Flash](#boot-on-usb-flash)
  * [Follow Instructions](#follow-instructions)
  * [Install Grub](#install-grub)
* [Install Packages](#install-packages)
  * [Primary Packages](#primary-packages)
  * [Side Applications](#side-applications)
  * [Terminal Applications](#terminal-applications)
* [Install Xfce](#install-xfce)
  * [Xubuntu-Desktop](#xubuntu-desktop)
  * [Uninstall Xfce](#uninstall-xfce)
* [Customize Xfce](#customize-xfce)
  * [Window Theme](#window-theme)
  * [Icon Theme](#icon-theme)
  * [Cursor Theme](#cursor-theme)
  * [Fonts](#fonts)
  * [Panel Preferences](#panel-preferences)
* [Customize Terminal](#customize-terminal)
  * [PowerLevel10k](#powerlevel10k)
  * [Customize Terminal Theme](#customize-terminal-theme)
* [Install I3wm](#install-i3wm)
  * []
* [Customize I3wm](#customize-i3wm)
* [Install Bash Scripts](#install-bash-scripts)
  * [Update](#Update)
  * [Weather](#weather)
  * [Change Mac Adress](#change-mac-adress)
* [Troubleshoot](#troubleshoot)
  * [Powerlevel10k Issue](#powerlevel10k-issue)
  * [LightDm](#lightdm)
  * [Grub Issue](#grub-issue)
* [Sources](#sources)
  * [Youtube](#youtube)
  * [Github](#github)
* [Credits](#credits)

## Introduction
This repository is made to help you in the complete installation of Ubuntu. At the end of this repo you will get a nice xfce4 fully nord customized on your ubuntu followed by I3wm and all it's customization as well. Some pictures are avaible in the [screens folder](https://github.com/ARU1-TEAM/Ubuntu-install/tree/main/screens) of the repository.
## Install Ubuntu
<p align="center"><img src="/screens/ubuntu.png" alt="ubuntu"></p>

### Create USB Flash
 - Download [Ubuntu iso file](https://ubuntu.com/#download) and select the latest version.
 - Download [balenaEtcher](https://www.balena.io/etcher/).
 - Load balena etcher, put iso file and select your usb key.
### Boot On USB Flash
 - Reboot your computer and press `DEL` key to get into your BIOS/UEFI.
 - Select your usb-key in the boot menu.
 - Save and exit.
### Follow Instructions
 - Select your language and click `Install Ubuntu`.
 - Select your keyboard layout. 
 - Select `Minimal installation` and both of the `Other options`. 
 - Select `Erase disk and install Ubuntu` (be carful, this option only works if you want to install the os on an empty disk , otherwise select the other option).
 - Select your region
 - Choose your name, computer's name, username and password.
 - Once the installation is finished, restart your computer.

### Install Grub

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

## Install Packages

### Primary Packages
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

### Side Applications
Install the user graphical applications 
~~~ sh
snap install spotify teams netflix-web vlc
sudo apt-get install flameshot gnome-calculator libreoffice
snap install code --classic
~~~

### Terminal Applications
~~~ sh
sudo apt-get install cava htop ranger neofetch cmatrix nano vim hollywood sl figlet
sudo add-apt-repository ppa:hsheth2/ppa
sudo apt-get install cava
~~~

### Install Xfce
### Xubuntu-Desktop
Install Xfce using this command
~~~ sh
sudo apt-get install xubuntu-desktop
~~~
Select lightdm to get vanilla Xfce 
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
- Create a `.themes` folder at your `~/`.
- Put the extracted file into the `.themes`.
- Select the theme in both `Window Manager` and `Appearance` settings like shown in the pictures.

### Icon Theme
Install Papirus Icon Theme.
~~~ sh
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
~~~
Go into appearance settings and select papirus-dark. 

### Cursor Theme
- First [download](https://www.pling.com/p/1505683/) the Lyrax theme.
- Create a `.icons` folder at your `~/`.
- Put the extracted file into the `.icons`.
- Then go into `Mouse and Touchpad settings` over the `Theme` tab and select your cursor theme. 

### Fonts
Install Cantarell font using this command.
~~~ sh
sudo apt-get install fonts-cantarell
~~~
Then you can select `Cantarell Regular` in both `Window Manager` and `Appearance` over the font tab.

### Panel Preferences
These are the modules to boot in the `Items Tab` in your `Panel Preferences`:


|              Items           |           
|:----------------------------:|
|       Whisker Menu           |
|     Separator (invisible)    |  
|        Window Buttons        |
| Separator (expend invisible) |
|        Workspace Switcher    |
|     Notification Area        |
|       PulseAudio Plugin      |
|    Separator (invisible)     |
|             Clock            |
|    Separator (invisible)     |

    
## Customize Terminal


### PowerLevel10k
Install these PowerLevel10k fonts 
- [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf]( https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)


Clone this repository
~~~ sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
~~~

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`
### Customize Terminal Theme
- Put a file named `example.theme` in `~/.local/share/xfce4/terminal/colorschemes` folder.
- Note that some folder might not be existing, so you might have to create them.
- Then you will have to select your theme in the `Appearance` tab of your xfce terminal.

Here you can find a [Nord Theme](https://github.com/ARU1-TEAM/Ubuntu-installation/tree/main/xfce4/Terminal/nord.theme), here a [Dracula Theme](https://github.com/ARU1-TEAM/Ubuntu-installation/tree/main/xfce4/Terminal/dracula.theme) and here a [Gruvbox Theme](https://github.com/ARU1-TEAM/Ubuntu-installation/blob/main/xfce4/Terminal/gruvbox.theme).

## Install I3wm

## Install Bash Scripts
- First go into the repository and go in the scripts folder using `cd scripts`.
- Then Make any script executable with this command 
~~~ sh
sudo chmod +x exmaple 
~~~
- Then put the script in the `~/usr/bin/` folder using this command
~~~ sh
cp example ~/usr/bin/
~~~
- And finaly you can run the script like any other script that is in ubuntu

### Update
The [Update Script](https://github.com/ARU1-TEAM/Ubuntu-installation/tree/main/scripts/update) will update every package that you have in your OS.

### Weather
The [Weather Script](https://github.com/ARU1-TEAM/Ubuntu-installation/tree/main/scripts/weather) will ask you your location and show you the weather forecasts

### Change Mac Adress
The [Change_Mac Script](https://github.com/ARU1-TEAM/Ubuntu-installation/tree/main/scripts/change_mac) will change your mac adress. Very userfull if you want to bypass the router blocking system.

## Troubleshoot
In case something doens't work. Make shure tu run the update command to see if the issue persists.
~~~ sh
sudo apt-get update
~~~
You can even upgrade your Ubuntu installion with.
~~~ sh
sudo apt-get upgrade
~~~
### PowerLevel10k Issue
If your powerlevel10k fonts doesn't match. Please check if you already put the proper fonts in your terminal preferences. In this case, you have to put the `MesloLGS NF Regular`
### LightDm
In case your xxfce is not the vanilla one. You can uninstall gdm3 (it is more likely that you installed it).
~~~ sh
sudo apt-get remove gdm3
~~~
Then install lightdm and enable it with theses commands.
~~~ sh
sudo apt-get install lightdm
sudo systemctl enable lightdm
~~~
And then reboot you computer to apply the changes. 
### Grub Issue
If you installed a new OS on your computer. Don't forget to update the grub so it can find it. Just do these commands
~~~ sh 
sudo os-prober 
sudo update-grub
~~~
It will normally detect your new OS. So now you can reboot and select what OS you want to use.
## Sources
For this Ubuntu-installation repository, we used several videos and githubs. All of them are listed down here in case you need it.
### Youtube
- We mainly used a Tech [Sama's video](https://www.youtube.com/watch?v=kZS84ctzii8&t=1546s) to install Ubuntu (french video). Click [here](https://www.youtube.com/channel/UCPP-NkzSqMJ9ywhJkcgrpAw) to see his channel.
- We also used [this video](https://www.youtube.com/watch?v=rKPoK_0hYwA&t=117s) to install xfce.
### Github
- This is the github for [PowerLevel10k](https://github.com/romkatv/powerlevel10k). To custom your terminal.

## Credits
This projet wad made by LumaGreen and Felixoux. We hope you really enjoyed it and it was helpfull. Feel free to contact us if something doens't work anymore, we will fix it ! 
Thank you for sharing 😊
