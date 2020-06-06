---
path: setup
date: 2020-06-06T11:48:11.548Z
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
[Cica](https://github.com/miiton/Cica)

https://github.com/miiton/Cica/releases/download/v5.0.1/Cica_v5.0.1_with_emoji.zip
からzipファイルをダウンロード
```
unzip ${ダウンロード先}/Cica_v5.0.1_with_emoji.zip -d ~/.fonts
```
# Install tools
- [Brave(webbrowser)](https://brave.com/ja/)
- [VsCode](https://code.visualstudio.com/download)
```sudo snap install code --classic```
- *[Docker](https://www.docker.com/get-started)
```
sudo apt install docker.io
sudo usermod -aG docker n18011
```


*sockの権限が必要なため、/var/run/docker.sockのパーミッションを666に変えた

# 共有フォルダ
exfatかntfsでフォーマットされている別のパーティションを~直下に自動でマウントする
```
// 共有したいdeviceのUUID調べる
blkid

// mountしたいdirを作成する(すでにあるなら良い)
mkdir ~/Work

// 自動マウントの設定
echo 'UUID=6A95-00EC /home/n18011/Work auto auto,x-systemd.automount,rw,nofail,x-systemd.device-timeout=1,suid,dev,exec,async,errors=remount-ro,username=n18011,uid=1000,gid=1000  0 1
' >> /etc/fstab
```


# Rust
[参考URL](https://doc.rust-jp.rs/book/second-edition/ch01-01-installation.html)
```
$ curl https://sh.rustup.rs -sSf | sh
$ cargo -V
cargo 1.44.0 (05d080faa 2020-05-06)
```

## rust tools
- [lsd](https://github.com/Peltoche/lsd)
```cargo install lsd```
- [tokei](https://github.com/XAMPPRocky/tokei)
```cargo install tokei```
- [bat](https://github.com/sharkdp/bat) ```cargo install --locked bat```
- [fd](https://github.com/sharkdp/fd)
```cargo install fd-find```
- [ripgrep](https://github.com/BurntSushi/ripgrep)
```cargo install ripgrep```
- [cargo atcoder](https://github.com/tanakh/cargo-atcoder)
```cargo install cargo-atcoder```

## lsを[lsd](https://github.com/Peltoche/lsd)に変更
```
alias ls='lsd'
alias l='ls -l'
alias la='ls -a'
alias lla='ls -la'
alias lt='ls --tree'
funcsave ls l la lla lt
```

# vscode extensions
- Japanese Languege Pack
- Docker
- Remote Containers
- Vim
- Material Icon Theme
- Code Runner(Run in Terminal: true)
- Bracket Pair Colorizer
- Auto Rename Tag
- indent-rainbow
- Rust
