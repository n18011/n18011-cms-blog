---
path: setup
date: 2020-06-02T11:48:11.548Z
title: ubuntu studio 20.04 SETUP
description: ubuntu studioをインストールしたので設定手順メモ
---
```
sudo apt install curl git exfat-fuse exfat-utils gparted
```
```
LANG=C xdg-user-dirs-gtk-update
```

# shell
```
sudo apt instal fish
sudo vi /etc/shells
/usr/bin/fish
chsh -s /usr/bin/fish
curl https://git.io/fisher --create-dirs -sLo ~/.config/fish/functions/fisher.fish
https://github.com/b-ryan/powerline-shell
```
# fonts
https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/JetBrainsMono
