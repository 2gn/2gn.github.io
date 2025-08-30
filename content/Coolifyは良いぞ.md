https://coolify.io/

セルフホストを滅茶苦茶簡単にしてくれるソフト。Dockerのファイルを書いて`Deploy`ボタンを押すだけでサーバーが立ち上がる。

(見た目はこんな感じ。今のところ、Home Assistant、Immich、paperless-ngxが動いている。本当はもっと動かしたいが、メモリが足りなかった。)
![[Pasted image 20250830233959.png]]

# Coolifyの良いところ
* インストールが簡単。コマンド一発
* サーバー管理がすべてwebフロントエンドで完結。==シェルにも入れる==
* [プリセットが豊富](https://coolify.io/docs/services/overview)。プリセットが用意されているサービスなら、自分でほとんど何もやらなくても数回クリックするだけで超簡単にサーバーを立てることができる。もちろん自分でDockerfile及びdocker-compose.ymlを弄ることも可能。
* Git/GitHub/Dockerfile/Docker-compose/データベース諸々に対応。
* カッコイイwebフロント。癒される。
* やったことはないが、sshで他のサーバーも管理画面に追加することができる。

