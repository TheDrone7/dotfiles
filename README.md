# Dotfiles

These are the dotfiles I use for my [Hyprland](https://hyprland.org) setup
on [Arch](https://archlinux.org/).

You will need an [AUR helper](https://wiki.archlinux.org/title/AUR_helpers) to install the dependencies.

---

## Dependencies

The following are the dependencies required to run the configuration files in this repository.
```shell
candy-icons-git sweet-cursors-hyprcursor-git sweet-gtk-theme-dark \
bat btop cava dunst dmenu foot lazygit neovim rofi pavucontrol \
waybar swaylock-effects-git grim slurp wl-clipboard notify-send \
hyprland hyprcursor hyprutils hyprwayland-scanner waybar-mpris-git \
xdg-desktop-portal-hyprland python rustup zsh swww-git jq pfetch
```

With `paru`
```shell
paru -Syu candy-icons-git sweet-cursors-hyprcursor-git sweet-gtk-theme-dark \
bat btop cava dunst dmenu foot lazygit neovim rofi pavucontrol waybar\
swaylock-effects-git grim slurp wl-clipboard notify-send hyprland \
hyprcursor hyprutils hyprwayland-scanner waybar-mpris-git \
xdg-desktop-portal-hyprland python rustup zsh swww-git jq pfetch
```

Also install the [Sweet Dark GTK theme](https://www.pling.com/p/1253385/)

---

### Installation
```shell
git clone https://github.com/TheDrone7/dotfiles.git
cd dotfiles
cp -r ./config/* ~/.config/
```

Next add execute perms for the scripts
```shell
# Notification sounds for dunst
chmod +x ~/.config/dunst/sounds/sound-normal.sh
chmod +x ~/.config/dunst/sounds/sound-critical.sh

# Scripts for waybar and hyprland
chmod +x ~/.config/hypr/scripts/tools/*
chmod +x ~/.config/hypr/scripts/*
chmod +x ~/.config/hypr/*

# Rofi - Power menu and App menu
chmod +x ~/.config/rofi/bin/*
```

### Wallpapers
The wallpapers are expected to be at `~/Pictures/Wallpapers/` and are named as `wallpaper.jpg`
It will randomly select a wallpaper from the directory and change it every 30 minutes.

You can modify this behaviour by changing `~/.config/hypr/scripts/wall`.
Refer to [swww repo](https://github.com/LGFae/swww/tree/main) to learn more.

To use the wallpapers in this repo, copy the wallpapers to `~/Pictures/Wallpapers/`
```shell
cp -r ./wallpapers/* ~/Pictures/Wallpapers/
```

### Shell

The shell used is `zsh` with `oh-my-zsh`.

```shell
# Install oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Copy the zshrc
cp ./zsh/zshrc ~/.zshrc
```

Feel free to modify the `zshrc` file to suit your needs.

### Neovim

```shell
# Install vim-plug
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'

# Open nvim and run :PlugInstall
nvim -c 'PlugInstall'
```

Vim should be good to go now too.

---

## Summary

```shell
# Dependencies
paru -Syu candy-icons-git sweet-cursors-hyprcursor-git sweet-gtk-theme-dark \
bat btop cava dunst dmenu foot lazygit neovim rofi pavucontrol waybar\
swaylock-effects-git grim slurp wl-clipboard notify-send hyprland \
hyprcursor hyprutils hyprwayland-scanner waybar-mpris-git \
xdg-desktop-portal-hyprland python rustup zsh swww-git jq pfetch

# Clone the repo
git clone https://github.com/TheDrone7/dotfiles.git
cd dotfiles

# Copy the config files
cp -r ./config/* ~/.config/

# Add execute perms
chmod +x ~/.config/dunst/sounds/*
chmod +x ~/.config/hypr/scripts/tools/*
chmod +x ~/.config/hypr/scripts/*
chmod +x ~/.config/hypr/*
chmod +x ~/.config/rofi/bin/*

# Copy the wallpapers
cp -r ./wallpapers/* ~/Pictures/Wallpapers/

# Install oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Copy the zshrc
cp ./zsh/zshrc ~/.zshrc

# Install vim-plug
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'

# Open nvim and run :PlugInstall
nvim -c 'PlugInstall'
```

---

### Credits
- [Hyprland](https://hyprland.org) for being amazing
- [Sweet theme](https://www.pling.com/p/1253385/) for the GTK theme, icons and cursor
- [Catppuccin theme](https://github.com/catppuccin) for beautiful colors
- [flick0/Aurora](https://archlinux.org/) for providing a starting point/inspiration
