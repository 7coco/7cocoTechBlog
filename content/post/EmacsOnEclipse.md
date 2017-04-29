+++
comments = true
date = "2017-03-31T14:35:07+09:00"
draft = false
slug = ""
tags = ["Eclipse","Emacs"]
title = "EclipseでEmacsキーバインドが使えなくなった"
topics = ["TIL",""]

+++

# 本日のTIL

## ぶつかった問題
QuickRex というパッケージを Eclipse にインストールしてみたところ、 Eclipse で Emacs キーバインドが使えなくなってしまいました……。

慌ててパッケージをアンインストール、 Eclipse の再起動を行うも Emacs キーバインドは使えず。

宮坂さんに [EclipseのClean起動](http://qiita.com/Yicr/items/8a9d86cd41a76fd078a7) を教わって試してみるも効果なく。

こうなればやむを得まいと Eclipse の再インストール を行っても効果がなく。

Eclipse の keys 設定を見に行くと scheme は Emacs になっているし実際によく使うショートカットを検索するときちんと設定されている……。

正直、もうだめだ！と思いましたw

## 解決法
__Eclipse の [環境設定] -> [General] ->  [keys] で使いたい Emacs キーバインドを探し、 `when` を `In windows` に変更。__

## 自分なりに解説
なぜだかわかりませんが ( タイミング的にインストールしたパッケージの影響と思われる ) ショートカットキーの多くの `when` が `Editing Text` になっていました。
`Editing Text` と言うといかにも正しい気がしますが、実はこれ「 全角入力の変換中 ( 変換の確定をする前で文字に下線が付いている時 ) 」のことなんです……。

つまりコードを書いている時のほとんどは `Editing Text`ではないということですね……。なんじゃそりゃ。

とりあえず  `In Windows` にするときちんと動くようになりました。
`In Windows` より `Editing Text` の方がしっくりくるのは私だけでしょうか……？

## まとめ
長く更新されていないパッケージをインストールすると比較的新しい機能やパッケージと競合してしまってよくわからない感じになる可能性がある。
Eclipse で Emacs キーバインドを使うのはそれなりの覚悟がいる。