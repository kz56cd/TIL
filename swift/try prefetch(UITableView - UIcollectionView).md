# try prefetch(UITableView / UIcollectionView)

## overview

### Pre-Fetching API とは

- iOS10で用意された
	- セルの事前読込
		- prefetch時に、画像キャッシュや通信など、処理のやや重いものを扱うことで、スクロールなどの安定化が期待できる
		- https://speakerdeck.com/toyship/ios10shi-dai-falsecollectionviewzui-xin-tukaikonasi
		
## usage

- prefetchのタイミング( = prefetchItemsAt)で、画像キャッシュのみ行う
	- 今回はNukeを利用していたため、NukeのPreheaterを使う
	- https://github.com/kean/Nuke#preheating-images
- UICollectionViewDataSourcePrefetching protocolに準拠
	- `collectionView.prefetchDataSource = self`

### prefetchItemsAt

```swift:
func collectionView(_ collectionView: UICollectionView, prefetchItemsAt indexPaths: [IndexPath]) {
    preheater.startPreheating(
        with: makeCacheRequests(indexPaths: indexPaths)
    )
}
    
private func makeCacheRequests(indexPaths: [IndexPath]) -> [Request] {
    return indexPaths.map { 
    	Request(url: viewModel.cellModels[$0.row].url) 
    }
}



### cancelPrefetchingForItemsAt

```swift:
func collectionView(_ collectionView: UICollectionView, cancelPrefetchingForItemsAt indexPaths: [IndexPath]) {
    preheater.stopPreheating(
        with: makeCacheRequests(indexPaths: indexPaths)
    )
}
```

## etc

上記はUICollectionViewの例となるが、UITableView
	- UITableViewDataSourcePrefetching
	- https://developer.apple.com/documentation/uikit/uitableviewdatasourceprefetching

## ref

- http://qiita.com/ayakix/items/d1910d63151f32a78347#uicollectionviewdatasourceprefetching%E3%81%AE%E5%AE%9F%E8%A3%85
- https://littlebitesofcocoa.com/242-pre-loading-images-with-uicollectionviewdatasourceprefetching