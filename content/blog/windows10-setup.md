---
path: windows10
date: 2020-06-08T13:09:56.469Z
title: windows10 setup
description: windows10をクリーンインストールした際のセットアップ手順メモ
---
# tools
- Brave
- Ubunttu(wsl2)

# 機能の有効化
- windows Subsystem for linux

# WSL2
## shell

sudo apt instal fish
sudo vi /etc/shells
/usr/bin/fish <-追記
chsh -s /usr/bin/fish
curl https://git.io/fisher --create-dirs -sLo ~/.config/fish/functions/fisher.fish

~/.config/fish/functions/fisher.fish
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

## fonts
Cica

https://github.com/miiton/Cica/releases/download/v5.0.1/Cica_v5.0.1_with_emoji.zip からzipファイルをダウンロード後zipファイルクリックCica-Regular.ttfクリック、インストール
wslウインドウ右クリックプロパティからフォント、Cicaを選択OK


## apt install
- cargo
## cargo install
- lsd
- bat
- tokei
## lsをlsdに変更
alias ls='lsd'
alias l='ls -l'
alias la='ls -a'
alias lla='ls -la'
alias lt='ls --tree'
funcsave ls l la lla lt
## PATH
export PATH="$PATH:/home/n18011/.cargo/bin"
