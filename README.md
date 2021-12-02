## Table of Contents

* [Introduction](#introduction)
* [Install Ubuntu](#install-ubuntu)
  * [Create USB Flash](#create-usb-flash)
  * [Boot On USB Flash](#boot-on-usb-flash)
  * [Follow Instructions](#follow-instructions)
* [Grub](#grub)
  * [Install Grub](#install-grub)
  * [Customize Grub](#customize-grub) 
* [Install Packages](#install-packages)
  * [Primary Packages](#primary-packages)
  * [Side Applications](#side-applications)
  * [Terminal Applications](#terminal-applications)
* [Xfce](#xfce)
  * [Install Xfce](#install-xfce) 
  * [Customize Xfce](#customize-xfce)
    * [Window Theme](#window-theme)
    * [Icon Theme](#icon-theme)
    * [Cursor Theme](#cursor-theme)
    * [Fonts](#fonts)
    * [Panel Preferences](#panel-preferences)
* [Uninstall Xfce](#uninstall-xfce)
* [Customize Terminal](#customize-terminal)
  * [Nano Synthax colors](#nano-synthax-colors)
  * [PowerLevel10k](#powerlevel10k)
  * [Customize Terminal Theme](#customize-terminal-theme)
* [I3wm](#i3wm)
  * [Install i3wm](#install-i3wm)
  * [Configure i3wm](#configure-i3wm)
    * [Mod Key](#mod-key)
    * [Shortcuts](#shortcuts)
    * [Display](#display)
  * [Customize i3wm](#customize-i3wm)
    * [Colors](#colors)
    * [Rofi](#rofi)
    * [Gaps](#gaps)
    * [Picom](#Picom)
    * [Polybar](#polybar)
    * [Fonts](#fonts)
  * [Rofi](#rofi)
    * [Install Rofi](#install-rofi)
    * [Customize Rofi](#customize-rofi)
  * [Uninstall i3wm](#uninstall-i3wm)
* [Install Bash Scripts](#install-bash-scripts)
  * [Update](#update)
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

## Grub
Grub is a simple way to set a dualboot on your computer. It is a bootloader.

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

### Customize Grub
You can find multiple grub Theme [here](https://www.pling.com/find?search=grub%20theme). But we will use the `tela` theme in our case. To install it, just do
~~~ sh
git clone https://github.com/vinceliuice/grub2-themes.git
cd grub2-themes
sudo ./install.sh -b -t tela
~~~
Now you can restart and you will see a beautifull grub !
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
snap install spotify teams netflix-web vlc discord
sudo apt-get install flameshot gnome-calculator libreoffice
snap install code --classic
~~~
Install LaTeX and TeXstudio. 
First, install LaTeX using 
~~~ sh
sudo apt-get install texlive-latex-extra
~~~
Then install TeXstudio using
~~~ sh
sudo add-apt-repository ppa:sunderme/texstudio
sudo apt-get install texstudio
~~~

### Terminal Applications
~~~ sh
sudo apt-get install htop ranger neofetch cmatrix nano vim hollywood sl figlet
sudo add-apt-repository ppa:hsheth2/ppa
sudo apt-get install cava
~~~

## Xfce

<p align="center"><img src="/screens/xfce-banner.png" alt="ubuntu"></p>

Xfce is a lightweight desktop environment for UNIX-like operating systems. It aims to be fast and low on system resources, while still being visually appealing and user friendly.

### Install Xfce
Install Xfce using this command
~~~ sh
sudo apt-get install xubuntu-desktop
~~~
Select lightdm to get vanilla Xfce 
Then run this command to enable lightdm, then you might reboot as well 
~~~ sh
sudo systemctl enable lightdm
~~~

### Customize Xfce

#### Window Theme
- First [download](https://www.gnome-look.org/p/1267246/) the nord theme.
- Create a `.themes` folder at your `~/`.
- Put the extracted file into the `.themes`.
- Select the theme in both `Window Manager` and `Appearance` settings like shown in the pictures.

#### Icon Theme
Install Papirus Icon Theme.
~~~ sh
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
~~~
Go into appearance settings and select papirus-dark. 

#### Cursor Theme
- First [download](https://www.pling.com/p/1505683/) the Lyrax theme.
- Create a `.icons` folder at your `~/`.
- Put the extracted file into the `.icons`.
- Then go into `Mouse and Touchpad settings` over the `Theme` tab and select your cursor theme. 

#### Fonts
Install Cantarell font using this command.
~~~ sh
sudo apt-get install fonts-cantarell fonts-inter
~~~
Then you can select `Cantarell Regular` in both `Window Manager` and `Appearance` over the font tab.

#### Panel Preferences
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

### Uninstall Xfce
To uninstall Xfce using this command
~~~ sh
sudo apt-get purge xfce4 xfconf xfce4-utils xfwm4 xfce4-session xfdesktop4 exo-utils xfce4-panel xfce4-terminal  thunar gdm3
sudo apt autoremove
~~~

## Customize Terminal

### Nano Synthax Colors
You can install Nano Synthax Highliting with only one command.
~~~ sh
curl https://raw.githubusercontent.com/scopatz/nanorc/master/install.sh | sh
~~~
And if you also want to see line numbers in nano, edit the `~/.nanorc` file and put `set linenumbers` at the very bottom. And there you go !

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

## I3wm
<p align="center"><img src="/screens/I3.png" alt="I3wm"></p>

I3 wm is a tiling window manager. It really helps being productive and it is really customizable. But it is not a desktop environement !

### Install i3wm

First we will install i3wm in the terminal by typing this command.
~~~ sh
sudo apt-get install i3
~~~
Now we can log out and switch from xfce-session to I3. Normally a prompt should appear on your screen and ask you if you want to generate th config file. Press `enter` for yes. Now another prompt will ask if you want to use the `win` key or the `alt` key for every shorcuts. Press the arrow keys to select the one that you want and press enter.

### Configure i3wm

Now we will configure everything and for that we have to press `$mod+enter` to get into the terminal. $mod is either the `win` or `alt`  key. It depends on what you chose earlier. 
Once you are in the terminal, type this command to modify the I3 configuration file. Remember it’s path, we will use it really often. 
There is a preconfigured config file in the repository in case you don’t want to configure it.
~~~ sh
nano ~/.config/i3/config
~~~

#### Mod Key

In case you want to change your mod key. Find the `set $mod ModX` at the beginning of the file. Replace the X with 1 or 4 like shown in the table right under.

|$mod   |key  |
|-------|-----|
|$mod1  |`Alt`|
|$mod4  |`Win`|


#### Shortcuts

To configure shortcuts set `bindsym $mod+ `and then the following key you want to press. For ewample we will run the terminal by pressing `alt+enter`. So we will do `bindsym $mod+enter exec xfce4-terminal`.

#### Display 
We will use xrandr to configure your displays settings. First we will install xrandr with this command :
``` sh
sudo apt-get install x11-xserver-utils
```
Now, we will edit the .profile file so that xrandr executes at each startup. To edit the file type :
``` sh
nano ~/.profile
```
If you don't no your screen name, just type `xrandr` in your terminal.
| Command |Result                               | Example        |
|:-------:|-------------------------------------|:--------------:|
| --output|Select the display                   |DP-1            |
| --mode  |Select the resolution                |1920x1080       |
|--rate   |Select display                       |144.00          |
|--primary|Put a screen on primary              |/               |
|--left-of|Put the the scree, on left of another|DVI-D-1         |
|--rotate |Rotate the screen                    |normal, inverted|

### Customize i3wm

#### Gaps
First install i3-gaps packages :
``` sh
sudo add-apt-repository ppa:regolith-linux/release
sudo apt-get install i3-gaps
```
To set gaps, type `inner gaps X` in `~/.config/i3/config` and replace X by anny value that you would like, 10 is good.

#### Picom
Picom is made do customize your i3wm. 
- Install it by running this command 
~~~ sh 
sudo apt-get install picom
~~~
- Then you need to locate your `picom.conf` file by doing this
~~~ sh
locate picom.conf
~~~
- Once you know it's location. You have to copy and paste it in `~/.config/picom/picom`. Some directories might not be existing, in this case you will have to create them. 
- If you don't have a `picom.conf` file, you can copy one form the repositroy in `I3wm/picom/picom.conf`.
- And finally put `exec_always --no-startup-id picom --experimental-backends` in your `~/.config/i3/config` file to run picom. 

#### Polybar
Polybar is a status bar that helps the user feel comfortable, it is quite usefull.
- First install all the dependencies with this command 
~~~ sh
sudo apt install build-essential git cmake cmake-data pkg-config python3-sphinx python3-packaging libuv1-dev libcairo2-dev libxcb1-dev libxcb-util0-dev libxcb-randr0-dev libxcb-composite0-dev python3-xcbgen xcb-proto libxcb-image0-dev libxcb-ewmh-dev libxcb-icccm4-dev libxcb-xkb-dev libxcb-xrm-dev libxcb-cursor-dev libasound2-dev libpulse-dev i3-wm libjsoncpp-dev libmpdclient-dev libcurl4-openssl-dev libnl-genl-3-dev
~~~
- Then git clone the polybar repository with 
~~~ sh
git clone https://github.com/polybar/polybar.git
cd polybar
sudo ./build.sh
~~~
- Type `Y` for everyprompt.
- Then put you polybar config in `~/.config/polybar/` if the polybar directory doesn't exist ,create it. You can take the config in the repository at `i3wm/polybar/config`.
- And lastly you have to put `exec_always --no-startup-id "killall polybar; polybar -r X"` in `~/.config/i3/config` to run polybar. Don't forget to change X to the name you gave your bar in `~/.config/polybar/config`. 
- You might have to reinstall i3-gaps because of polybar.

### Rofi 
Rofi is a menu to search applications. 
#### Install Rofi
To install it, simply type
~~~ sh
sudo apt-get install rofi
~~~
#### Customize Rofi
If you want to customize Rofi, follow the next steps. 
- First create `.Xressources` file in `~/`.
- There is an example for the nord theme down there
Change the colors as you wich
~~~ 
rofi.color-enabled: true
rofi.color-window: #4c566a, #5e81ac, #434c5e
rofi.color-normal: #4c566a, #5e81ac, #4c566a, #81a1c1
rofi.color-active: #ff0000, #00ff00, #0000ff, #268bd2
rofi.color-urgent: #393939, #f3843d, #393939, #268bd2
rofi.font:                            Inter 13
rofi.hide-scrollbar:                 true
~~~
- Once you finished do not forget to type the following command to apply the changes.

~~~ sh
xrdb .Xressources
~~~
### Uninstall i3wm

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
First install macchanger by doing 
~~~ sh
sudo apt-get install macchanger
~~~
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
For this Ubuntu-installation repository, we used several videos and githubs. All of them are listed down here in case you need them.
### Youtube
- We mainly used a Tech [Sama's video](https://www.youtube.com/watch?v=kZS84ctzii8&t=1546s) to install Ubuntu (french video). Click [here](https://www.youtube.com/channel/UCPP-NkzSqMJ9ywhJkcgrpAw) to see his channel.
- We also used [this video](https://www.youtube.com/watch?v=rKPoK_0hYwA&t=117s) to install xfce.
### Github
- This is the github for [PowerLevel10k](https://github.com/romkatv/powerlevel10k). To custom your terminal.

## Credits
This projet was made by LumaGreen and Felixoux. We hope you really enjoyed it and it was helpfull. Feel free to contact us if something doens't work anymore, we will fix it ! 
Thank you for sharing 😊
