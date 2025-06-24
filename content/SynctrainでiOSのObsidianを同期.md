#synctrain #obsidian #syncthing

> [!info]
> ### 結論
> [Synctrain](https://forum.syncthing.net/t/beta-test-my-new-ios-app-for-syncthing/22457)という、iOSのSyncthingクライアントでObsidianのフォルダを同期することができた。
> 
# 動機

iOSでObsidianを同期するのには、従来、iCloudを使うかObsidian Syncというものを契約する必要があった。
![[obsidian-sync-pricing.png]]

高すぎる。
## Syncthingを使いたい

Syncthingはサーバーレスなので、無料。しかし、従来のiPhone用のSyncthingクライアントのMobius Syncは、無料で30MBまでしか同期できないどころか、Obsidianのフォルダに同期することができない。

もう少し探すと、[Synctrainという新しいクライアントのベータテストがある](https://forum.syncthing.net/t/beta-test-my-new-ios-app-for-syncthing/22457)ことに気がついた。

# やり方

## 事前に必要なもの
* 同期したいObsidianのVault
* iOS端末
* 同期元の端末

## (同期元)Syncthingクライアントのインストール
[公式のGetting Startedガイド](https://docs.syncthing.net/intro/getting-started.html)を参考のこと。

## (同期先iOS) Synctrainのインストール


以下のリンクでtestflightに参加する。ベータテストなので。
TestFlightのアプリが必要。

https://testflight.apple.com/join/2f54I4CM


## Syncthingの設定

[公式のGetting Startedガイド](https://docs.syncthing.net/intro/getting-started.html)を参考のこと。

フォルダのIDは同じものにする必要がある。

### フォルダIDがzef56-k9oafの例
#### Synctrain
![image](synctrain-folder.jpeg)

#### Syncthing
![[syncthing-folder.png]]