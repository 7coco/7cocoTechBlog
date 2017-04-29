+++
comments = true
date = "2017-03-30T14:27:49+09:00"
draft = false
slug = ""
tags = ["Java","正規表現"]
title = "Java の正規表現でぶつかった"
topics = ["TIL",""]

+++

# 03/30のTIL

## では早速本日のTIL
### ぶつかったこと
Java を書く中で正規表現で文字の "[" や "]" にマッチさせたいと思って、頭の中でこんな感じに思い浮かべました。
```
 Pattern.compile("[[]]");
```
いやいやこれじゃメタ文字の `[]` になっちゃうよと思い、実際にはこう書きました。
```
Pattern.compile("[\[\]]");
```
ただしこれは
> Invalid escape sequence (valid ones are  \b  \t  \n  \f  \r  \"  \'  \\ )

と言われます。
「ん？じゃあエスケープしなくていいの？」と思い、最初に頭に思い浮かべたものを書くと、今度はコンパイルできました。
ところが、実行してみるとこう言われます。

> Exception in thread "main" java.util.regex.PatternSyntaxException: Unclosed character class near index 3

### 解決法
結論としてはこうすれば動きます。
```
Pattern.compile("[\\[\\]]");
```

### 自分なりに解説
`[]` のままでは文字ではなく正規表現のメタ文字として評価されてしまうというのは正しかったです。
ただ、ならば  `\` でエスケープして `\[\]` とすればいいかというとそれだけではダメです。
Java では文字列中で `\` を表すには `\` を用いてエスケープする必要があるからです。
結果として `\\[\\]` になります。
もちろん、`[` `]` に限らず、正規表現内でエスケープが必要な文字は全て、 __正規表現のエスケープとしての `\` と Java の文字列のエスケープとしての `\` の二つが必要__ です。


以上、2017/03/30 の TIL でした。