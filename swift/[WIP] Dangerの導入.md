# [WIP] Dangerの導入

## overview

- wip

## usage

```
```

### organizationのprivate repoなので少しめんどくさい

- machine userとなるアカウントを新規に作成する
	- http://www.wikihow.com/Use-Deploy-Keys-on-Github#Creating_a_Machine_User_sub
	- machine user参考：https://developer.github.com/v3/guides/managing-deploy-keys/#machine-users
- 追加したいprivate repoにcollaboratorとしてadd
- personal access token を作成する
	- 権限はrepo全てにチェックすること

### CIへのtoken登録

#### bitrise

- workflow editor のEnv Vars タブをクリック
- DANGER_GITHUB_API_TOKENという名称で先に用意したpersonal access tokenをadd


## ref

- http://qiita.com/toshihirooya/items/2d2a3c28071892d909e5
- http://qiita.com/toshiya/items/589834d9b09c0dbe4c56
- http://sssslide.com/speakerdeck.com/jp_pancake/dangerwoshi-tuteprwozi-dong-de-nitietukusuru


bundle install
bundle exec danger




------------

	- https://gist.github.com/ismail-syed/f8e34d32535374b1fd1e67c6448edb6f

- machine userにする必要はない（と思われる）
- http://qiita.com/n_slender/items/886d9313a5ab5877dbf9




jsにはrequested_reviewersというのが存在するが、ruby側にはないっぽい



m.sano@ohako-inc.jp



## etc

### Danger plugin

- Plugins の項を参照：
	- http://danger.systems/ruby/

### 良さそうなplugin

#### clorox

- file header(署名)の形式チェック？
	- https://github.com/barbosa/danger-clorox

#### todoist

- TODO/FIXMEの記述に対し細かな通知ができる
	- https://github.com/hanneskaeufler/danger-todoist

#### slather
 
- コードカバレッジの可視化
	- https://github.com/BrunoMazzo/Danger-Slather

### pluginの作成

- http://blog.duck8823.com/entry/2017/07/11/155714


20170912_add_danger