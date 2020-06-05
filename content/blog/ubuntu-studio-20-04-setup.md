---
path: setup
date: 2020-06-02T11:48:11.548Z
title: ubuntu studio 20.04 SETUP
description: ubuntu studioをインストールしたので設定手順メモ
---
```
// CLI　web server command
sudo apt install curl 
// version managiment
sudo apt install git 
// exfat patch
sudo apt install exfat-fuse exfat-utils
// partition managiment 
sudo apt install gparted
```
```
// change directory languege of ~ dir
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
# Install tools
- Brave webbrawser


# 共有フォルダ
exfatかntfsでフォーマットされている別のパーティションを~直下に自動でマウントする
```
// 共有したいdeviceのUUID調べる
blkid

// mountしたいdirを作成する(すでにあるなら良い)
mkdir ~/Work

// 自動マウントの設定
/etc/fstabで
UUID="blkidで調べたUUID" /home/n18011/Work auto, .... 0 2

を追記

```

# lsを変更
exa
alias ls="exa"
