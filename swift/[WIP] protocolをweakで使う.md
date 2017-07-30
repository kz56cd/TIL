# [WIP] protocolをweakで使うには

## overview

- protocolはそのままではweakで使用できない
	- その場合は、protocolにclassを継承させればよい
	- class継承すると、EnumやStructで該当のprotocolは使用できなくなる
	
> そもそもプロトコル、構造体、列挙体はweakにできないが、クラスおよびクラスを継承したものだけはweakに出来る。

- http://qiita.com/yimajo/items/892bd2fe1ccb808ffe49

## usage

```
protocol Hoge {
    func hogeFunc()
}

protocol Fuga: class {
    func fugaFunc()
}

class FooClass {
    weak var hogeVar: Hoge? // NG
    weak var fugaVar: Fuga? // OK
}
```


## etc

- stub