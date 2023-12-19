## Debian 12 dotfiles and window manager files


# Install a base Debian12 without Desktop Enviroment.  
I tend to install some base tools before I snapshot a vBoxVM. 

```bash
apt install sudo curl git neovim nano zsh zplug
```

# if you used to give root a password and direct access you need to allow the non-root user to run sudo
# I do that by editing sudoers file with visudo and leave the default group like [%sudo   ALL=(ALL:ALL) ALL]
# visudo will take your system default editor (nano,vim etc. )

afterwards you need to add your non-root user to the sudo group
#Add user to sudo group   
``` bash
usermod -aG sudo $USERNAME
```

I prefer the zsh as default shell 
# set zsh default shell
```bash
chsh -s /bin/zsh
```

# for git you can use your git account details  in your home directory 
```bash
git config --global user.name "USERNAME" 
git config --global user.email "EMAIL@xxxxxxxx"
```

# If you plan to use docker set docker access for the non root user
# Add docker group
```bash
   sudo groupadd docker
```
# Add your current user to docker group
```bash
  sudo usermod -aG docker $USER
```
# Switch session to docker group
```bash
  newgrp - docker
```
# Run an example to test
```bash
   docker run hello-world
```


# For dwm
```bash
   sudo apt install xserver-xorg-core xserver-xorg-video-amdgpu xinit xinput x11-xserver-utils 
   
```


```bash
   sudo apt install alacritty 
```




# prepare your config directories in your home directory

```bash
   mkdir -p ~/.config/sway ~/.config/waybar ~/.config/wofi
```



# add a wallpaper by copying it to  ~/.config/sway/wallpaper.jpg

# make sure that the scripts in .config/sway are executable 
```bash
   chmod +x ~/.config/sway/*.sh
```




# Keyboard Shortcuts

(Shift, Super) q: Quit active app
(Shift, Super) e: Exit sway itself
(Super) t: Open a terminal
(Super) space: Application launcher
(Super) escape: Lock the screen
(Super) any arrow key: Move focus to another app/quadrant
(Shift, Super) any arrow key: Move the active window in the direction of the arrow you pressed
(Super) r: Resize the active window
(Super) any number: Switch to that numbered workspace
(Shift, Super) f: Toggle floating mode
(Super) s: Create a stack

