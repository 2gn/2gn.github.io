公式のドキュメントだと最初っからフレーバーをインストールさせられるので分りづらかった。

> [!note]
> # 結論
> https://docs.syncthing.net/users/autostart.html#using-systemd

これ見てもパッと見てわからないので、完結に書くと

# 1. 証明書入れる
```
sudo mkdir -p /etc/apt/keyrings
sudo curl -L -o /etc/apt/keyrings/syncthing-archive-keyring.gpg https://syncthing.net/release-key.gpg
```

# 2. レポジトリ入れる(stable)
```
echo "deb [signed-by=/etc/apt/keyrings/syncthing-archive-keyring.gpg] https://apt.syncthing.net/ syncthing stable" | sudo tee /etc/apt/sources.list.d/syncthing.list
```

# 3. Syncthing入れる

```
sudo apt-get update
sudo apt-get install syncthing
```

# 4. systemdをenableする

```
systemctl enable syncthing@<ユーザー名>.service
systemctl start syncthing@<ユーザー名>.service
```


---

WebUIは[8384ポート](http://localhost:8384)で動いている。