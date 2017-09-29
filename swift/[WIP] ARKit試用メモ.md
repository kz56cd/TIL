# [WIP] ARKit試用メモ

<!--## overview
## usage
## ref-->

- ARKit-Sampler
	- https://qiita.com/shu223/items/e55e1426c9e036254761

### 任意の3Dデータを使う

https://qiita.com/noby111/items/dd883e9097fd6ce22893

- daeをModels.scnassetディレクトリ配下に置く(xcode上で自動認識される)
- daeをscnにコンバートする
	- > Xcodeのメニュー ＞ Editor ＞ Convert to SceneKit scene file format (.scn)
- scnファイルのEuler x を -90にする

### タップを検知し、現実世界の座標を取得する

- hitTestを使う
	- https://developer.apple.com/documentation/arkit/arframe/2875718-hittest
- 返り値[ARHitTestResult] が空の時
	- > 結果は、ジャイロの初期化などが、完了していないと、取得に失敗することがありますので、isEmptyで取得できているかどうかを確認しています。
	- http://dev.classmethod.jp/smartphone/ios-11arkit-measure/