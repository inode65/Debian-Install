# Debian 12 dotfiles and window manager files


### Install a base Debian12 without Desktop Enviroment.  
I tend to install some base tools before I snapshot a vBoxVM. 

```bash
apt install sudo curl git neovim nano zsh zplug
```

### if you used to give root a password and direct access you need to allow the non-root user to run sudo
### I do that by editing sudoers file with visudo and leave the default group like [%sudo   ALL=(ALL:ALL) ALL]
### visudo will take your system default editor (nano,vim etc. )

afterwards you need to add your non-root user to the sudo group
###Add user to sudo group   
``` bash
usermod -aG sudo $USERNAME
```

I prefer the zsh as default shell 
### set zsh default shell
```bash
chsh -s /bin/zsh
```

### for git you can use your git account details  in your home directory 
```bash
git config --global user.name "USERNAME" 
git config --global user.email "EMAIL@xxxxxxxx"
```

### If you plan to use docker set docker access for the non root user
### Add docker group
```bash
   sudo groupadd docker
```
### Add your current user to docker group
```bash
  sudo usermod -aG docker $USER
```
### Switch session to docker group
```bash
  newgrp - docker
```
### Run an example to test
```bash
   docker run hello-world
```


### For dwm
```bash
   sudo apt install xserver-xorg-core xserver-xorg-video-amdgpu xinit xinput x11-xserver-utils libx11-dev libxinerama-dev libxft-dev
```


```bash
   sudo apt install build-essential make alacritty firefox-esr pipewire  
```





### prepare your config directories in your home directory

```bash
   mkdir -p ~/.config
   cd .config
   git clone https://git.suckless.org/dwm 
   cd dwm
  ```

### set alacritty as terminal 
### static cons char *termcmd change st to alacritty
   
```bash
    nano config.def.h
```

### cp config.def.h to config.h
### make
### sudo make install 


```bash
   cd ~./config 
   git clone https://git.suckless.org/dmenu
   cd dmenu
   sudo make install 
```

```bash
   cd 
   nvim .xinitrc
   exec dwm

```

