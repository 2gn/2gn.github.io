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

プロキシを設定したスマホでhttp://mitm.itにアクセス

書いてある手順にそって証明書をダウンロード、インストール

# 結果

![[Pasted image 20250215234600.png]]

こんな感じでパケットを見ることができる。
パケットごとの情報も見ることができる。

![[Pasted image 20250215234901.png]]
