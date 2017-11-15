# homebrew usage

## 目次

- fomulaを過去バージョンに戻す

### fomulaを過去バージョンに戻す

今までローカルにインストールしたバージョンを確認

```
$ brew info swiftgen
```

戻したいバージョンを指定して切り替え

```
$ brew switch swiftgen 5.0.0
```

ref:
http://tech.withsin.net/2015/10/01/brew-switch/


### brewに自作アプリケーションを登録する

1. `brew tap`用の空リポジトリを作成（名称は`homebrew-[name]`にする）
2. パッケージ情報を記述したrubyファイルをpush

以下実行

```shell:
$ brew tap user_name/name
$ brew install app_name
```

ref:
https://qiita.com/masawada/items/484bbf83ef39cad7af74