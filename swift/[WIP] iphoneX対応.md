# [WIP] iphoneX対応

### 注意すべきところ

> - UITableViewCell#contentView のサイズに従っていない
> - UIToolBarではなく自前のバーを使っている
> - View内のコンテンツを自分でレイアウトしている(UITableViewなど使っていない)

http://blog.lisb.direct/entry/2017/12/11/100000

- **`contentInsetAdjustmentBehavior` はiOS11以降なので、下位対応は必要**
	- contentInsetAdjustmentBehaviorについて：https://qiita.com/iganin/items/afbadb2d2b052d7b9ee9

### 他tips / memo

- https://qiita.com/yuukiw00w/items/05df49c509fa041f0f55
- safe area近くをアプリ背景色で塗りつぶしたりした
- apple の動画解説
	- http://tech.wonderpla.net/entry/2017/10/31/110000
- iphoneX対応が不十分だとリジェクトされる可能性もある、とのこと