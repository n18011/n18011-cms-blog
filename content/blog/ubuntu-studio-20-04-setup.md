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
/usr/bin/fish <-追記
chsh -s /usr/bin/fish
curl https://git.io/fisher --create-dirs -sLo ~/.config/fish/functions/fisher.fish
https://github.com/b-ryan/powerline-shell
mkdir -p ~/.config/powerline-shell && \
powerline-shell --generate-config > ~/.config/powerline-shell/config.json
```
```json
{
  "segments": [
    "virtual_env",
-   "username",
-   "hostname",
    "ssh",
    "cwd",
    "git",
    "hg",
    "jobs",
    "root"
  ]
}
```
# fonts
参考URL https://github.com/miiton/Cica

https://github.com/miiton/Cica/releases/download/v5.0.1/Cica_v5.0.1_with_emoji.zip
```
unzip ${ダウンロード先}/Cica_v5.0.1_with_emoji.zip -d ~/.fonts
```
