---
title: Pandocチュートリアル 第1回 Pandocでドキュメントを変換しよう
author: 藤原 惟 / すかいゆき (@sky\_y)
date: 2017年1月20日
revealjs-url: reveal.js-3.4.0
theme: sky-sky-y
transition: fade
transitionSpeed: fast
slideNumber: true
history: true
slideNumber: true
margin: 0
...

# このスライドをどう作ったか

----

# reveal.jsのライブラリを入れる

- [Releases · hakimel/reveal.js](https://github.com/hakimel/reveal.js/releases) の「Downloads」にあるzipまたはtar.gzをダウンロードし、展開する
- フォルダの中身のうち、**index.html以外**を全て目的のフォルダにコピーする

----

# Markdownを書く

- PandocのMarkdownで書く
    - [Pandoc - Pandoc User’s Guide](http://pandoc.org/MANUAL.html#pandocs-markdown)
- このスライド自体はGitHub Pagesでアップされています
- ソースコード:

----

# pandoc

```
$ pandoc -s index.md -t revealjs -o index.html
```

----

# 例: connpassのHTMLからMarkdownを求めたい

----

# 準備の際に実際にやりました

- オーガナイザーさんにconnpassページ原稿を渡したい
- やっぱりMarkdownで書きたい
    - [connpass自体はMarkdown記法を持っている](http://help.connpass.com/organizers/markdown)
- 藤原はconnpassの本イベントページを編集する権限がない
    - **そうだ、HTMLをPandocで読み込めば、Markdownがゲットできる！！**

----

# connpassのHTMLを取得

- [Pandocチュートリアル 第1回 - connpass](https://haskell-with-skype.connpass.com/event/48446/)
- メニューアイコン（または右クリック）で「ソースを表示」
- そのまま`Command-S (Ctrl-C)`でHTMLを保存(`connpass.html`とする)

----

# Q: このMarkdownは何の方言に近いか？

- [connpassで使えるMarkdown記法 - connpass ご利用ガイド](http://help.connpass.com/organizers/markdown)
- ヒント
    - `http://connpass.com URLは自動的にリンクになります。`
        - <http://connpass.com>  URLは自動的にリンクになります。

----

# A: GitHub Flavored Markdown(gfm)に近い

- Pandocのデフォルトで使えるMarkdown方言のうち、自動リンク記法はgfmが対応
- このように、出所の分からないMarkdown仕様でも、ある程度なら処理系を推測できる
    - 今後の課題として、メジャーなサービスについて方言を比較できるようにしたい

----

# PandocでMarkdownに変換

```
$ pandoc connpass.html -t markdown_github -o connpass.md
```

----

# 質問

- Slackにて受け付けます
- TwitterでもOKです
    - [\@sky\_y \| Twitter](https://twitter.com/sky_y)
