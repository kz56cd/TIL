# [WIP] pasoriセットアップ / nfcタグwriteまで

- 1: 諸々入れる
	- https://qiita.com/alt-core/items/abc83b3c1e2dd176717f
- 2: pipで入れた後に、githubからもcloneする
	- http://uchan.hateblo.jp/entry/2016/11/18/190237
- http://blog.nikuniku.me/entry/%3Fp%3D322_1


---------


### pip
http://blog.nikuniku.me/entry/%3Fp%3D322_1



### nfcpyのsample

- cloneして使う
- https://github.com/nfcpy/nfcpy/tree/master/examples

#### examples/tagtool.py

nfcタグ / Felicaの情報読み取りができる

```
[ohako-pc@ nfcpy] (master=)$ examples/tagtool.py
[nfc.clf] searching for reader on path usb
[nfc.clf] using SONY RC-S380/P NFC Port-100 v1.11 at usb:020:006
** waiting for a tag **
```

- タイムズカーシェア
	- `Type3Tag 'FeliCa Lite-S (RC-S966)' ID=012E390165C94F7F PMM=00F1000000014300 SYS=88B4`
- suica
	- `Type3Tag 'FeliCa Standard (RC-S???)' ID=01140214AB14BD06 PMM=100B4B428485D0FF SYS=0003`
- NFCタグ
	- `Type2Tag 'NXP NTAG213' ID=040B700A835681
NDEF Capabilities:
  readable  = yes
  writeable = yes
  capacity  = 137 byte
  message   = 0 byte`
  
  
  
  
> python ndeftool.py make smartposter -t PlalaPinky https://www.youtube.com/watch?v=M5eDef_aBlM | python tagtool.py load -
  
  
ndeftool.py make smartposter -t PlalaPinky https://www.youtube.com/watch?v=M5eDef_aBlM | tagtool.py load -


ndeftool.py make smartposter -t PlalaPinky https://www.youtube.com/watch?v=M5eDef_aBlM  
  


## protocol等

- NFCReaderSessionProtocol
  
  
  
python ndeftool.py make smartposter https://www.youtube.com/watch?v=M5eDef_aBlM


メゾン大平公園、〒330-0856 埼玉県さいたま市大宮区三橋１丁目５２−１



	
	
