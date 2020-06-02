---
path: hardware
date: 2020-06-01T11:00:51.521Z
title: ' Portable SSDにOSをいれてPClessになろう'
description: portable SSDにOSをインストールしbootできるようにする
---
# 背景
----
私は普段ノートPCをメインに2年ほど使っております。  

現在使用中のPC内臓のHDDの容量は512GBありますがデュアルブートしているということもあり、流石に2年使っていると容量も足りなくなってきたのでPortableSSD1TBを購入しました。

1TBの容量をデータのみに使用するのも私の使い方だと持て余すし、PCでセットで毎回持ち歩くのもどうかと思ったのでOSを持ち運びたくなりました。

OSを持ち運びするにあたって、元々インストール用のUSBメモリがあるという知識はあったのでOS用のUSBメモリもあるだろう。

 そしてUSBメモリがあるならポータブルSSDでもいけるだろうと調べた結果、手元の環境でPortableSSDを実現できたので手順をここにメモしておく。

# 概要
----
## 前提
ディスクの記録領域を変更する操作が含まれています。

PortableSSDの作成手順は**私の環境固有の問題**も含まれているため、参考にはしても鵜呑みにしないでください。

## 環境

### Hardware/OS
- PC(UEFI)
- windows10(Home)
- ubuntu18.04
- USBメモリ 16GB
- 外付SSD  1TB


**SDD初期構成**

partition|format|size|OS
------------|:-----------:|:-------------:|------------
未割り当て||1TB|


### 使用するツール
#### CLI
- GParted
- Diskpart
- grub-install

#### GUI

## 目的

### 目標SSD構成
partition|format|size|OS
------------|:-----------:|:--------------:|:-----------
/dev/sdb1|fat32|200MB|
/dev/sdb2|ntfs|128GB|windows10
/dev/sdb3|ext4|128GB|UbuntuStudio20.04
/dev/sdb4|linux-swap|8GB|
/dev/sdb5|exfat|512GB|*
未割り当て||200GBくらい|

*/dev/sdb5はUbuntuStudio20.04の/homeパーティションを割り当てています。
