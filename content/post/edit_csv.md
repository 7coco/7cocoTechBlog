+++
comments = true
date = "2017-04-11T14:53:56+09:00"
draft = false
slug = ""
tags = ["csv",""]
title = "Mac で CSV を編集するときの個人的イチオシツール"
topics = ["TIL",""]

+++

# 本日のTIL

## ぶつかったこと
新規アグリコードを書いていたら、CSVを編集しなければならなくなり、Mac で CSV をいい感じに編集できるものを探すことになりました。
一応、前提として私は以下のような状況でした。
- excel は持ってない。高い。
- Numbers で編集すると拡張子が .numbers になったものを編集してることになってややこしいし、なぜか Numbers で開くと空白とか書式が勝手に Numbers 的によしなにされてしまうらしく、余計な差分が出まくる。
- 普段 atom を使っている ( やっぱり atom が一番だよね！ )

## 解決法
### 結論
####  [tablr](https://atom.io/packages/tablr) というパッケージを atom にインストール

## 自分なりに解説
解説というか、一応使い方みたいなところを書いておきます。
### インストール
```bash
apm install tablr
```
### 使い方
`tablr` がインストールされた状態で csv ファイルを開くと下のような画面が出てきます。

![image.png (68.8 kB)](https://files.esa.io/uploads/production/attachments/2264/2017/04/15/19884/8c0009c4-ece7-4f70-8962-2d175eb2a4b0.png)

「Open Table Editor」で表になった状態で編集できる画面が、「Open Text Editor」で通常のテキストベースでの編集ができます。

#### OpenTableEditor
![image.png (97.9 kB)](https://files.esa.io/uploads/production/attachments/2264/2017/04/15/19884/3dd59f07-e5fb-47dc-95a1-300567fa50a6.png)

OpenTableEditor を選択するとこんな感じに表示されます。
セルの編集はもちろん複数選択やコピペなどができて、普通の表を編集する時に求めるような機能はだいたいあると思います。
一応 [こちら](https://github.com/abe33/atom-tablr/blob/master/docs/cheatsheet.md) がチートシートになっているので、あの機能はどうやったら使えるんだ？という時には覗くときっと見つかると思います。
基本的な編集は直感的に行えますので、あまり複雑なことをしなければ導入にあたっては苦労しない気がします。

## まとめ
やはり普段使っているエディタを使うのが慣れるのも早く、導入もスムーズでいいですね。
atom は新しい言語のシンタックスハイライトやリンターなどに代表されるように、様々なパッケージが常に作られていて、それを手軽にインストールすることができるので便利です。
まともなエディタならみんなそうだと言われてしまうとその通りだと思いますが、私はやっぱり atom が一番慣れているのでw
