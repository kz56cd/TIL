# 【入門】Elm 

## memo

### 環境構築もろもろ

- インストール方法各種あるが、homebrewで各種対応できる
- version確認
	- `elm make -h`
- elm-formatをbrewで入れた場合シンボリックリンク通す必要がある
	- `ln -s /usr/local/bin/elm-format-0.18 /usr/local/bin/elm-format`
	- https://github.com/avh4/elm-format/issues/126#issuecomment-248711775
- シンタックスハイライト
	- https://github.com/edubkendo/atom-elm

## 基本文法

- http://elm-lang.org/docs/syntax

## ElmとFRP

`Signal` がversion 0.18よりduplicatedに

- 経緯など
	- https://qiita.com/chuck0523/items/28b07968a941d8d493d2
- > しかし、ElmアーキテクチャはFRPを知ると、よりアーキテクチャ自体の理解が進むのではないのかと思います。非同期的なデータフロープログラミングであるということを念頭に置くだけでも、Elmアーキテクチャのそれぞれの要素の相互関係がわかりやすくなるのではないでしょうか。

	- https://qiita.com/3tty0n/items/0f559505efa6256d22d7


## ref

- https://www.gitbook.com/book/giisyu/elm_usui_book/details
- http://dev.jgs.me/2015/02/05/get-start-elm.html
