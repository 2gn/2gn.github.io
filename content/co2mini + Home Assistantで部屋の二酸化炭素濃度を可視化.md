
家に[co2mini](https://honeshabri.hatenablog.com/entry/CO2-mini)が転がっていたので、Home Assistantに入れてみた。

## 方針
* [co2mini (cliツール)](https://github.com/jerr0328/co2mini)を使って、co2miniを==MQTTデバイスとして==Home Assistantに認識させる。

## 必要なもの
* co2miniを繋ぐサーバー
* Home Assitantのサーバー
* 家のネットワーク

# 1. MQTTブローカーを立てる

MQTTは、IoT機器同士が通信するためのプロトコル。MQTTブローカーは、その中心となるサーバーのこと。MQTT機器は、全て一旦MQTTブローカーに接続する。

MQTTブローカーは、いくつかの方法で立てることができる。

## 1.1. Home AssitantのMosquitto Brokerを使用する方法

Home Assistant OS、もしくはHome Assistant Supervisedを使用している場合は、公式のMQTTブローカーアドオンが使える。
https://github.com/home-assistant/addons/blob/master/mosquitto/DOCS.md

僕はDockerで動かしているのでアドオンは入れられなかった。

## 1.2. Mosquittoを自分で立てる方法
Mosquittoブローカーを外部で自分で立てることもできる。

僕は[[Coolifyは良いぞ|Coolifyを使った]]ので簡単だったが、調べると結構大変そうだった。

# 2. Home AssistantのMQTTを設定する

参考: https://www.home-assistant.io/integrations/mqtt/#setting-up-a-broker

# 3. co2miniを認識させる
[このサイト](http://trashbox.homeip.net/nownow/20200510/co2mini-logger.php)に従って、サーバーがco2miniを認識するようにする。何気にこれが一番大変。事前に、USB-Microのケーブルが通信可能なものかを確認しておくことをおすすめする。

# 4. co2miniのcliツールを入れる

[これ](https://pypi.org/project/co2mini/)をツールとしてインストールする。僕は[uv](https://docs.astral.sh/uv)で入れた。

```shell
uv tool install co2mini
```
# 5. co2miniの設定

[公式のドキュメント](https://github.com/jerr0328/co2mini)の通り、`/etc/co2mini.env`を以下の内容で作成する。

```
MQTT_ENABLED=true
MQTT_BROKER=localhost <--MQTTブローカーが立っている場所
```

# 6. co2miniのsystemdを作る
以下を`/etc/systemd/system/co2mini.service` として保存する

<iframe frameborder="0" scrolling="no" style="width:100%; height:416px;" allow="clipboard-write" src="https://emgithub.com/iframe.html?target=https%3A%2F%2Fgithub.com%2Fjerr0328%2Fco2mini%2Fblob%2F4fa44ef4c1ec75d728496c38f0f3508f98f752ca%2Fco2mini.service%23L1C1-L16C27&style=default&type=code&showBorder=on&showLineNumbers=on&showFileMeta=on&showFullPath=on&showCopy=on"></iframe>


その後、`sudo systemctl daemon-reload && sudo systemctl enable co2mini && sudo systemctl start co2mini`

`sudo systemctl status co2mini`で、ちゃんとMQTTブローカーに接続しているか確認。

# 7. Home Assistantからco2miniを設定

co2miniがMQTTブローカーに接続できていれば、Home Assistantのentityにco2miniが追加されているはずだ。

(co2メーターを設定してみた例。だいたい1000ppmから良くない。1000ppmを越えるとDiscordにメッセージが届くように設定してある。残念ながら、換気扇は自動で回らないので、僕がワークフローに組込まれている)
![[Pasted image 20250830232835.png]]

(二酸化炭素の推移。何時に何人家に帰ってきたかが分る)

![[Pasted image 20250830232947.png]]
