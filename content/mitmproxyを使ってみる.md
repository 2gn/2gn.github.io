#programming #network #technology
# mitmproxyのインストール (debian)

```
sudo apt install mitmproxy
```

# mitmproxyサーバーを立てる

ポート番号が8080の例

```
mitmproxy -p 8080
```

# スマホ側でプロキシを設定

Settings -> Wi-Fi -> Network Name -> Configure Proxy -> Manualにて、

Server: mitmproxyが動いてるパソコンのIP
Port: 上で使ったポート番号

## 証明書のインストール

プロキシを設定したスマホで[http://mitm.it](http://mitm.it)にアクセス

書いてある手順にそって証明書をダウンロード、インストール

# 結果

![[mitmproxy-packet-list.png]]

こんな感じでパケットを見ることができる。
パケットごとの情報も見ることができる。

![[mitmproxy-packet-info.png]]

中身が色々見れて面白い。