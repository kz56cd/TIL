# WKWebViewのCookieの扱い

## overview

- 以前は永続化などは行ってなかったが、現在は自動で対応してくれてるみたい？

- WKWebViewは `WKWebsiteDataStore` にてCookieやcacheの管理をしている
	- デフォルトでは自動でCookieの永続化(store / set)を行っているようです
		- https://developer.apple.com/documentation/webkit/wkwebsitedatastore/1532937-default
		- 念のため `webView.configuration.websiteDataStore.isPersistent` をprintしたが `true` が返ってきた
		- （参考）WKWebViewの変更点など： http://qiita.com/ShingoFukuyama/items/a9bf7d26f9dd889d3297#%E3%83%97%E3%83%A9%E3%82%A4%E3%83%99%E3%83%BC%E3%83%88%E3%83%A2%E3%83%BC%E3%83%89%E3%81%8C%E5%AE%9F%E8%A3%85%E5%8F%AF%E8%83%BD%E3%81%AB	
