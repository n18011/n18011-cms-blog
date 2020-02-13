---
path: programming
date: 2020-02-13T03:27:54.062Z
title: Next.jsとGatsby.jsの違い
description: 完全備忘録
---
webアプリを作りたくて、あるサイトを見てNextとGatsbyの違いについて調べました。その結果、Nextを採用することにしました。ですが、Nextではやりづらい部分があったので調べ直してみると先程のサイトではできないと思って採用を見送ったGatsbyでもできそうなのでここでは私個人のNextとGatsbyの違いについてまとめる。


*参考にはしないでください


## Next
SSR(Server Side Rendering)を行う。
ブラウザで閲覧する前に静的なサイトを生成する。その後は通常のSPA(Single Page Appreciation)のように動作


ここから個人の印象
- PWA(Progressive Web Appreciation)に向かない気がする
- 利用できるホスティングサービス限られると思う


## Gatsby
静的サイトジェネレータ。動的サイトにも対応できる。ビルド時に静的なサイトを生成する。

ここから個人の印象
- データ更新を全体に反映するもの(CMS等)が多い場合には向かない印象
- Localにデータを持ち、操作する分には問題なさげ(buildし直す必要ないため)
- PWAに向いている


