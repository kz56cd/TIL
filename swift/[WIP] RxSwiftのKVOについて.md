# RxSwiftのKVOについて

- KVO(RxSwift公式)
	- https://github.com/ReactiveX/RxSwift/blob/master/Documentation/GettingStarted.md#kvo
- 2種ある
	- observe
	- observeWeakly
	
## 違い

observeWeaklyは弱参照になる。それ以外の大きな違いはなさそう？
-> 通常使用はobserveWeaklyの方がよさそう

> rx_observeも同じ動作をしますが、強参照になるためrx_observeWeaklyを使用したほうがいいです。

https://qiita.com/syou007/items/60e84366a97ee28757bc

> observe でretainSelf=trueだと、レシーバーを強参照してしまうので、注意が必要です
→ retainSelf=false または、 observeWeakly を使うほうがベターかもしれません。

https://blog.sgr-ksmt.org/2016/12/27/uitabbarcontroller_rx/

> rx.observeWeakly has somewhat slower than rx.observe because it has to handle object deallocation in case of weak references.

https://github.com/ReactiveX/RxSwift/blob/master/Documentation/GettingStarted.md#kvo

## unregisterしないでVCが消えた場合に、メモリリークするのか

unregister ≒ disposable (rxSwiftの場合)

公式ではないですが、以下のように `addDisposableTo` するのがよさそうです(KVOの項を参照)

> ```
> someSuspiciousViewController
    .rx.observeWeakly(Bool.self, "behavingOk")
    .subscribe(onNext: { behavingOk in
        print("Cats can purr? \(behavingOk)")
    })
    .addDisposableTo(disposeBag)
> ```

https://www.gitbook.com/book/victorqi/rxswift/details

あとBindingsの項にあったのですが、（不要なときもあるものの）基本つけとくのが公式オススメとのことです

> Official suggestion is to always use .addDisposableTo(disposeBag) even though that's not necessary for simple bindings.

https://www.gitbook.com/book/victorqi/rxswift/details



### おまけ、rxSwiftのDisposeBagについて

#### 仕組み

> 仕組みはごくシンプルで、このようにsubscribeで出たゴミをメソッドチェインでゴミ箱に捨てておくと、DisposeBagがよきタイミングでDisposableを破棄してくれる。
> 
> (中略)
> 
> addDisposableToは引数に渡されたゴミ箱 (DisposeBag)にゴミをinsertしている。
> 
> ```
> public func addDisposableTo(_ bag: DisposeBag) {
    bag.insert(self)
}
> ```
> DisposeBagの実装を見てみるとこれまたシンプルで、自身がdeinitされたタイミングで溜まっているゴミを破棄するようになっている。

#### DisposeBagに捨てないとどうなるのか？

completedのハンドリングが結構めんどう（らしい）ので、素直に `addDisposableTo` する方がいいかもしれないです

> コードによって以下のような書き方をされてる時があって、これってどうなるんだっけ・・・と疑問に思ったことがあったけど、ここまでに書いた通りでEventがcompletedになったタイミングで解放される。逆にcompleteされない状態が長く続く場合は明示的にdisposeしないといけない。

https://horimisli.me/entry/rxswift-memory-management/








https://qiita.com/syou007/items/d527b4486c34686d0acd