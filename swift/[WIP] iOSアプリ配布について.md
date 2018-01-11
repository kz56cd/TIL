# [WIP] iOSアプリ配布について

## overview

- まずは以下を確認する
	- 【公式】アプリケーション配布作業の流れについて
	- https://developer.apple.com/jp/documentation/IDEs/Conceptual/AppDistributionGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40012582-CH1-SW1

### 個人開発

- Apple IDを作る
- Apple Developer Programに登録
- 証明書 / デバイス登録など諸々行い、開発スタート
- (βテスト) **省略してもよい**
- itunes connectにてアプリをアップロード / 申請

### 組織開発

（Organizationのチームエージェント権限アカウントから、新たに開発メンバーを招待したい場合）

#### 招待する側

- Menber centerより、招待したい人のemail(Apple id未作成でもよい)を登録
	- 権限の設定を行う
		- (注意：Menber権限の場合、デバイス登録など細かな権限がないのでAdmin権限にした方が良い)
- (招待者がMenber centerのpeopleに登録されたことを確認したら)itunes connectに招待する

#### 招待された側

- 招待メールのリンクを踏む
	- Apple IDに（未登録の場合）登録する
	- App Developer Programに（未登録の場合）登録する
- 証明書 / デバイス登録など諸々行い、開発スタート
- (βテスト) **省略してもよい**
- itunes connectにてアプリをアップロード / 申請 


### 注意

- 先にApple Developer Programに登録必要がある
	- > 当初iTunes Connectにアクセスできるのは、Apple Developer Programに加入した者だけです。
	- https://developer.apple.com/jp/documentation/IDEs/Conceptual/AppDistributionGuide/UsingiTunesConnect/UsingiTunesConnect.html#//apple_ref/doc/uid/TP40012582-CH22-SW3
