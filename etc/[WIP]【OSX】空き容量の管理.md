# [WIP]【OSX】空き容量の管理

## tips

### purge

```
$ sudo purge
```

### sleepimageの削除

- high sierraの場合は面倒
	- https://github.com/mathiasbynens/dotfiles/issues/811

```
$ sudo rm /private/var/vm/sleepimage
```

生成を禁止： `sudo pmset -a hibernatemode 0`

### キャッシュファイルの削除

- https://disk-diag.en.softonic.com/mac


## etc

- ディスクの占有データを可視化
	- 
