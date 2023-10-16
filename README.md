# Linux_Rice

**BSPWM**
![Rice_2](https://github.com/miscellaneous-mice/Linux_Rice/assets/79500624/ce9f41fa-e112-464c-95b0-ee02386ab8c3)

**Xmonad**
![image](https://github.com/miscellaneous-mice/Linux_Rice/assets/79500624/80ac4689-de5f-4b66-8cf4-254e4ae4ad6b)

## Base Installation

1) Arch Install
  - https://github.com/miscellaneous-mice/Arch-install
    
2) BSPWM minimal install
  - https://github.com/miscellaneous-mice/BSPWM

  *------------------ or ------------------*

2) Xmonad minimal install
  - https://github.com/miscellaneous-mice/Xmonad

3) Post installation stuff (Not necessary, but if you're daily driving WM it helps)
  - https://github.com/miscellaneous-mice/Extra-Configurations-Linux

**Note :** *You might wanna change the config files after the minimal install. Steps to change these configurations are given below.*
  - Make a backup folder in Home directory ```mkdir ~/Backup```
  - Make this directory for rofi and xmobar ```mkdir ~/.local/bin```
  - To store screenshots make this folder ```mkdir ~/Pictures ~/Pictures/Screenshots```
  - git clone this repository in home directory ```git clone https://github.com/miscellaneous-mice/Linux_Rice.git```
  - Download all the dependencies [Dependencies](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#packages-dependencies)
  - [Setting theme](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#setting-themes-icons-fonts-mouse-cursors)
  - [Configuring init files](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-init-files)
  - [Configuring Window manager files](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-window-manager-files)
  - [Configuring AUR helper](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-aur-helper)
  - [Configuring neovim](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-neovim)
  - [Configuring rofi](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-rofi)
  - [Configuring xmobar for Xmonad](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-xmobar-xmonad) or [Configuring polybar for BSPWM](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-polybar-bspwm)
  - [Configuring alacritty](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#adding-alacritty-themes)
  - [Neofetch themes](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#configuring-neofetch-themes)
  - [Starship themes](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#starship-terminal)
  - [Rice terminal](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#to-make-rice-setup-complete)
  - [Extras](https://github.com/miscellaneous-mice/Linux_Rice/tree/main#some-changes-you-need-to-make-for-your-pc)


## Packages dependencies
- To download these packages just do ```sudo pacman -S {package-name}```
- code 
- feh 
- firefox
- thunar
- alsa-utils
- alacritty
- rofi
- scrot
- lxappearance
- otf-font-awesome
- ttf-ubuntu-font-family
- Starship (https://starship.rs/)
- rofi-calc
- Firefox theme -> https://addons.mozilla.org/en-US/firefox/addon/plum-torte/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search

## Setting themes, icons, fonts, Mouse cursors.
- First download these files into the Downloads folder
  - Theme -> https://www.gnome-look.org/p/1687249
  - Icons -> https://www.gnome-look.org/p/1305251
  - Fonts -> Given below
    - https://www.nerdfonts.com/font-downloads (Jetbrains nerd fonts) [For both]
    - https://www.nerdfonts.com/font-downloads (Iosevka nerd fonts) [For BSPWM]
    - https://www.nerdfonts.com/font-downloads (Mononoki nerd fonts) [For Xmonad]
  - Mouse cursor -> https://www.gnome-look.org/p/1197198
- Make the appropriate directories so lxappearance can recognise them
```
$ cd ~/
$ mkdir .icons .themes .fonts
```
- Download the appropriate tools for unzipping files
```
$ sudo pacman -S unzip
```
- Extract the downloaded files into appropriate directories. First cd into the folder where you've downloaded
```
$ tar -xf Dracula.tar.xz -C ~/.themes/
$ tar -xf candy-icons.tar.xz -C ~/.icons/
$ tar -xf Bibata-Modern-Ice.tar.xz -C ~/.icons/
$ unzip JetBrainsMono.zip [For both]
$ unzip Iosevka.zip [For BSPWM]
$ unzip Mononoki.zip [For Xmonad]
$ mv *.ttf ~/.fonts/
```
- Open lxappearance and set the themes you like. For configuring mouse cursor appropriately look into [Setting a cursor theme](https://github.com/miscellaneous-mice/My_Linux_config/blob/main/README.md#setting-a-cursor-theme)
- Set the wallpaper ```feh --bg-fill ~/Linux_Rice/wallpaper/street.png```


## Configuring Window manager files
- For BSPWM
  - First move files to backup folder
  ```
  $ mv ~/.config/bspwm/bspwmrc ~/Backup/
  $ mv ~/.config/sxhkd/sxhkdrc ~/Backup/
  ```
  - Now replace these config files into its appropriate directory
  ```
  $ cp ~/Linux_Rice/.config/bspwm/bspwmrc ~/.config/bspwm/
  $ chmod +x ~/.config/bspwm/bspwmrc
  $ cp ~/Linux_Rice/.config/sxhkd/sxhkdrc ~/.config/sxhkd/
  ```
- For Xmonad
  - First move files to backup folder
  ```
  $ mv ~/.xmonad/xmonad.hs ~/Backup/
  ```
  - Now replace these config files into its appropriate directory
  ```
  $ cp ~/Linux_Rice/.xmonad/xmonad.hs ~/.xmonad/
  ```

## Configuring init files
- Replace this content in present ```~/.bashrc``` file
```
$ mv ~/.bashrc ~/Backup/
$ cp ~/Linux_Rice/.bashrc ~/
```
- Replace the contents of ```~/.bash_profile```
```
$ mv ~/.bash_profile ~/Backup/
$ cp ~/Linux_Rice/.bash_profile ~/
```
- Replace the contents of ```~/.xinitrc```
```
$ mv ~/.xinitrc ~/Backup/
$ cp ~/Linux_Rice/.xinitrc ~/
```

## Configuring AUR helper
### Yay AUR helper
```
$ git clone https://aur.archlinux.org/yay.git
$ cd yay
```
- Compile the package
```
$ makepkg -si
```

## Configuring neovim
- Uncomment this line[10] in .bashrc file : ```vim ~/.bashrc```
```
$ alias vim=nvim
```
- Delete vim and install neovim to avoid any errors
```
$ sudo pacman -R vim
$ sudo pacman -S neovim
```
- First make the config direcotory
```
$ mkdir ~/.config/nvim/
```
- Copy the config file into the config directory
```
$ cp ~/Linux_Rice/.config/nvim/init.vim ~/.config/nvim/
```

## Configuring neofetch themes

**Using my neofetch theme**
- First replace the contents of neofetch in config folder
```
mv ~/.config/neofetch ~/Backup
cp -r ~/Linux_Rice/.config/neofetch ~/.config/
```
**Using other neofetch themes**
- First git clone this repo
```
$ git clone https://github.com/Chick2D/neofetch-themes.git
```
- Make the config directory for neofetch
```
$ mkdir ~/.config/neofetch
```
- Copy whatever themes you like to your config directory
```
$ cp ~/neofetch-themes/small/dotfetch.conf ~/.config/neofetch/
$ mv ~/.config/neofetch/dotfetch.conf ~/.config/neofetch/config.conf
```
- References
  - https://github.com/Chick2D/neofetch-themes


## Setting a cursor theme
- In ```~/.xinitrc``` add the following line. Only for xmonad..!!
```
xsetroot -cursor_name left_ptr
```
- If to get this folder ```~/.icons/default/index.theme``` change the all themes, icons, mouse cursor in lxappearance to default, then back to our theme (i.e. dracula, candy-icons, bibata)
- First edit the ```~/.icons/default/index.theme```
```
[icon theme] 
Inherits=Bibata-Modern-Ice
```
- Next edit the gtk-theme ```~/.config/gtk-3.0/settings.ini```
```
[Settings]
gtk-cursor-theme-name=Bibata-Modern-Ice
```
- References
  - https://wiki.archlinux.org/title/Cursor_themes


## Configuring xmobar (Xmonad)
- move previous .xmobarrc file into backup folder
```
$ mv ~/.xmobarrc ~/Backup/
```
- Copy the pacman update file and make it executable
```
$ cp ~/Linux_Rice/.config/xmobar/pacupdate ~/.local/bin/
$ chmod +x ~/.local/bin/pacupdate
```
- Make a xmobar directory
```
$ mkdir ~/.config/xmobar
```
- copy the new xmobar file into the config directory
```
$ cp ~/My_Linux_config/xmobar/xmobarrc ~/.config/xmobar/
```

## Configuring rofi
- For BSPWM
```
$ mv ~/.config/rofi ~/Backup/
$ cp -r ~/Linux_Rice/.config/rofi ~/.config/
```
- For Xmonad
```
$ sudo pacman -R dmenu
$ sudo pacman -S rofi
$ mkdir ~/.config/rofi
$ cp -r ~/Linux_Rice/.config/rofi/* ~/.config/rofi/
```

### Configuring rofi power menu
- First get into rofi directory in this github repo
```
$ cd ~/My_Linux_config/rofi/
```
- Copy the rofi-power-menu into ~/.local/bin folder
```
$ cp ~/Linux_Rice/.local/bin/rofi-power-menu ~/.local/bin/
```
- Make the file executable
```
$ chmod +x ~/.local/bin/rofi-power-menu
```
- References
  - https://github.com/jluttine/rofi-power-menu/tree/master


## Configuring polybar (BSPWM)

- Move the the polybar config files to backup folder
```
$ mv  ~/.config/polybar ~/Backup/
```
- Configure polybar
```
$ cp -r ~/Linux_Rice/.config/polybar ~/.config/
```
- Make the files executable
```
$ chmod +x ~/.config/polybar/config.ini
$ chmod +x ~/.config/polybar/launch.sh
```
- References
  - https://github.com/neoryans/dotfiles-bspwm/tree/main/.config

## Adding alacritty themes

- Replace the alacritty config files
```
$ mv ~/.config/alacritty/alacritty.yml ~/Backup/
$ cp ~/Linux_Rice/.config/alacritty/* ~/.config/alacritty/
```
### If you want more themes
- First go into alacritty config directory
```
$ cd ~/.config/alacritty/
```
- Git clone this repo
```
$ git clone https://github.com/eendroroy/alacritty-theme.git
```
- Change the existing import line in ```~/.config/alacritty/alacritty.yml```
```
import:
 - ~/.config/alacritty/alacritty-theme/themes/{theme}.yaml
```
- References
  - https://github.com/eendroroy/alacritty-theme

## Starship terminal
- First install starship
```
$ curl -sS https://starship.rs/install.sh | sh
```
- Apply the preset
```
$ starship preset pure-preset -o ~/.config/starship.toml
```
- Git clone and install the powerline fonts
```
$ git clone https://github.com/powerline/fonts.git --depth=1
$ cd fonts
$ ./install.sh
```
- Change font in ```~/.config/alacritty/alacritty.yml```
```
font:
  normal:
    family: Source Code Pro for Powerline

  bold:
    family: Source Code Pro for Powerline

  italic:
    family: Source Code Pro for Powerline

  bold_italic:
    family: Source Code Pro for Powerline

  size: 11
```
- References
  - https://github.com/powerline/fonts
  - https://starship.rs/presets/#pure-prompt


## To make rice setup complete
- Installing colorscripts. See [guide](https://gitlab.com/dwt1/shell-color-scripts)
  ```
  $ yay -S shell-color-scripts
  ```
  - Add this line to your ```~/.bashrc``` file
  ```
  colorscript -e alpha
  ```
- Installing pipes. To execute see [guide](https://github.com/pipeseroni/pipes.sh#contents)
  ```
  $ git clone https://github.com/pipeseroni/pipes.sh.git
  $ cd pipes.sh
  $ sudo make install
  ```
- Installing tty clock terminal. To execute see [guide](https://github.com/xorg62/tty-clock/blob/master/README)
  ```
  $ git clone https://github.com/xorg62/tty-clock.git
  $ cd tty-clock
  $ sudo make install
  ```
- Installing unimatrix. To execute just type ```$ unimatrix```. See [guide](https://github.com/will8211/unimatrix)
  ```
  $ curl -L https://raw.githubusercontent.com/will8211/unimatrix/master/unimatrix.py -o ~/.local/bin/unimatrix
  $ chmod a+rx ~/.local/bin/unimatrix
  ```
  - Add this to your ```~/.bashrc``` file
  ```
  alias unimatrix="~/.local/bin/unimatrix -c blue -u 'Linux'"
  ```

## Some changes you need to make for your PC
- In ```~/.xinitrc``` files you might need to replace the display name and resolution with yours. Find display name by ```$ xrandr```
```
xrandr --output {display-name} --mode {resolution}
```
- In ```~/.xinitrc``` uncomment according to your window manager
```
[For Xmonad]
exec xmonad

[For bspwm]
exec bspwm
```
- You might need to change some configurations in polybar like battery adapter name. Wifi adapter name etc.

## If Xmonad breaks after update try this
- First open the ttyl terminal from login screen ```ctrl + alt + F2```
- Recompile the xmonad package ```$ xmonad --recompile```
- Start xmonad using ```$ startx```

