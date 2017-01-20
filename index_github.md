------------------------------------------------------------------------

簡単な自己紹介
==============

------------------------------------------------------------------------

準備: Pandocをインストールする
==============================

------------------------------------------------------------------------

このスライドを自分で作ろう
==========================

------------------------------------------------------------------------

Pandocで作れるスライド
======================

-   今回は「reveal.js」形式に変換
    -   HTML+JavaScriptによるプレゼンテーション
-   Pandocでは他のプレゼン形式にも変換できる
    -   LaTeX Beamer
    -   reveal.js以外のHTMLプレゼン（割愛）

------------------------------------------------------------------------

実際のソースコード
==================

-   このスライド自体はGitHub Pagesでアップされています
-   GitHubリポジトリ: <https://github.com/sky-y/haskell-skype-pandoc-1>
    -   Markdown (raw): <https://raw.githubusercontent.com/sky-y/haskell-skype-pandoc-1/master/index.p.md>

reveal.jsのライブラリを入れる
=============================

-   本来の手順
    -   [Releases · hakimel/reveal.js](https://github.com/hakimel/reveal.js/releases) の「Downloads」にあるzipまたはtar.gzをダウンロードし、展開する
    -   フォルダの中の`index.html`を書き換えて、ダブルクリックするとそのままブラウザで動く
-   今回
    -   テーマ(CSS)をカスタマイズしている
        -   このスライドでは`sky`をカスタマイズしたCSS(`sky-sky-y`)を作った
        -   上記のGitHubリポジトリの「reveal.js-3.4.0/css/theme」に置いている

------------------------------------------------------------------------

Markdownを書く
==============

-   PandocのMarkdownで書く
    -   [Pandoc - Pandoc User’s Guide](http://pandoc.org/MANUAL.html#pandocs-markdown)
        -   [Pandoc ユーザーズガイド 日本語版](http://sky-y.github.io/site-pandoc-jp/users-guide/)

------------------------------------------------------------------------

ヘッダに色々書く
================

-   ヘッダには2種類ある
    -   Title block (`%`ではじまる、簡潔)
    -   YAML metadata (`---`ではじまり`...`でおわる、高機能)
        -   テンプレート内で使用するための変数を埋め込める
-   詳細はユーザーズガイドの「[Producing slide shows with pandoc](http://pandoc.org/MANUAL.html#producing-slide-shows-with-pandoc)」を参照

------------------------------------------------------------------------

    ---
    title: Pandocチュートリアル 第1回 Pandocでドキュメントを変換しよう
    author: 藤原 惟 / すかいゆき (@sky\_y)
    date: 2017年1月20日
    revealjs-url: reveal.js-3.4.0
    theme: sky-sky-y
    transition: fade
    （略）
    ...

------------------------------------------------------------------------

pandocコマンド
==============

    $ pandoc index.p.md -s -t revealjs -o index.html

-   `-s`: standalone (ヘッダ付きの完全なファイルを出力)
-   `-t`: 出力フォーマット(reveal.js)
-   `-o`: 出力ファイル名

------------------------------------------------------------------------

例: connpassのHTMLからMarkdownを求めたい
========================================

------------------------------------------------------------------------

準備の際に実際にやりました
==========================

-   オーガナイザーさんにconnpassページ原稿を渡したい
-   やっぱりMarkdownで書きたい
    -   [connpass自体はMarkdown記法を持っている](http://help.connpass.com/organizers/markdown)
-   藤原はconnpassの本イベントページを編集する権限がない
    -   **そうだ、HTMLをPandocで読み込めば、Markdownがゲットできる！！**

------------------------------------------------------------------------

connpassのHTMLを取得
====================

-   [Pandocチュートリアル 第1回 - connpass](https://haskell-with-skype.connpass.com/event/48446/)
-   メニューアイコン（または右クリック）で「ソースを表示」
-   そのまま`Command-S (Ctrl-C)`でHTMLを保存(`connpass.html`とする)

------------------------------------------------------------------------

Q: このMarkdownは何の方言に近いか？
===================================

-   [connpassで使えるMarkdown記法 - connpass ご利用ガイド](http://help.connpass.com/organizers/markdown)
-   ヒント
    -   `http://connpass.com URLは自動的にリンクになります。`
        -   <http://connpass.com> URLは自動的にリンクになります。

------------------------------------------------------------------------

A: GitHub Flavored Markdown(gfm)に近い
======================================

-   Pandocのデフォルトで使えるMarkdown方言のうち、自動リンク記法はgfmが対応
-   このように、出所の分からないMarkdown仕様でも、ある程度なら処理系を推測できる
    -   今後の課題として、メジャーなサービスについて方言を比較できるようにしたい

------------------------------------------------------------------------

PandocでMarkdownに変換
======================

    $ pandoc connpass.html -t markdown_github -o connpass.md

------------------------------------------------------------------------

質問
====

-   Slackにて受け付けます
-   TwitterでもOKです
    -   [@sky\_y | Twitter](https://twitter.com/sky_y)

