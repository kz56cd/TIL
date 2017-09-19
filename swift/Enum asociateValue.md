# Enum asociateValue

## overview

- Enum型に値を格納できる

### どんなケースで使うべきか

- （仮に）エクセル上にマトリクス構造化できるケースのうち、
	- 虫食いで限定箇所があるものは、asociate valueが向いてる
	- （全て共通であれば、structで総当り的に作ればよい）

イメージ：

||a|b|c|d|
|:--|:--|:--|:--|:--|
|1|x|○|○|x|
|2|○|x|○|○|
|3|○|○|○|x|

## [WIP] usage

宣言：

```
enum Sports {
    case running
    case tennis(ballType: BallType)
    case basketBall(playerNum: Int, ballType: BallType)
}

enum BallType {
    case soft
    case hard
}
```

使用例、switchで評価する時はletなどで変数化する必要がある：

```
let myFaboriteSports = .tennis(ballType: .hard)

switch myFaboriteSports {
case .running:
    // do something
    break
case tennis(let ballType):
    break
case basketBall(let playerNum, let ballType):
    break
}

```

## ref

- http://qiita.com/gologo13/items/0d484da7d4c9beb9e0b1#associated-value

----

## etc

- `==` などで比較したいとき
	- Equatableに準拠させる：
	- http://blog.ishkawa.org/2016/09/25/1474824960/
	