# try prefetch(UITableView / UIcollectionView)

## overview

- iOS10以降
	- セルの読み込みが安定する
	- https://speakerdeck.com/toyship/ios10shi-dai-falsecollectionviewzui-xin-tukaikonasi

## usage

- prefetchのタイミング( = prefetchItemsAt)で、画像キャッシュのみ行う
	- 今回はNukeを利用していたため、NukeのPreheaterを使う
	- https://github.com/kean/Nuke#preheating-images
- UICollectionViewDataSourcePrefetching protocolに準拠
	- `collectionView.prefetchDataSource = self`

### prefetchItemsAt

```
func collectionView(_ collectionView: UICollectionView, prefetchItemsAt indexPaths: [IndexPath]) {
    preheater.startPreheating(
        with: makeCacheRequests(indexPaths: indexPaths)
    )
}
    
private func makeCacheRequests(indexPaths: [IndexPath]) -> [Request] {
    return indexPaths.map { Request(url: viewModel.cellModels[$0.row].url) }
}


```

### cancelPrefetchingForItemsAt

```
func collectionView(_ collectionView: UICollectionView, cancelPrefetchingForItemsAt indexPaths: [IndexPath]) {
    preheater.stopPreheating(
        with: makeCacheRequests(indexPaths: indexPaths)
    )
}
```


## ref

- http://qiita.com/ayakix/items/d1910d63151f32a78347#uicollectionviewdatasourceprefetching%E3%81%AE%E5%AE%9F%E8%A3%85
- https://littlebitesofcocoa.com/242-pre-loading-images-with-uicollectionviewdatasourceprefetching