# [WIP]frameworkを自作する

<!--# overview

# usage

# ref
-->

ログ
https://ohako-inc.slack.com/archives/C4AGFPJMU/p1506044695000134

# overview

- 作るのは簡単
	- https://speakerdeck.com/lovee/nanikorenanikore-playground-gashi-eru-framework-sutugoi
- でもハマりポイントが多い（特にxib使う時とか）
	- import側、schemeをsharedにしてなかった
	- xibにcustom classを指定しても認識しない
		- `2017-09-22 10:11:03.120 ImgCarouselViewSample[1561:18856] Unknown class ImgCarouselView in Interface Builder file.`
		- **Moduleはimportしたプロジェクト名を指定する**
		- （補完はどうも効かないらしい）
	- publicになってないやつはないか？
	- Clean build folder + Delriverd Data削除 + 再ビルド
	- [WIP]Nibではまる
	- [WIP]NSBundleではまる
- playgroundが動かない（同じくnot load Nib）


-------



- https://ja.stackoverflow.com/questions/18772/%E8%87%AA%E4%BD%9C%E3%83%95%E3%83%AC%E3%83%BC%E3%83%A0%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%92import%E3%81%99%E3%82%8B%E3%81%A8-no-such-module-%E3%81%AE%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%8C%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%82%8B