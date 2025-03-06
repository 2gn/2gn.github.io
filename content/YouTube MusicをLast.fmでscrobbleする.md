
# 必要なもの
* [uv](https://docs.astral.sh/uv/)
* git


# レポジトリをクローンする

(オリジナルはos.environを使っていますが、僕が勝手にgetenvに変更しました。)
```shell
$ git clone https://github.com/2gn/youtube-music-scrobbler
```

## Last.fmのAPIを取得

ここから
https://www.last.fm/api/account/create

## APIを設定
`.env`ファイルを作成し、以下のように記述する。

```python
LAST_FM_API="<LAST FM APIのキー>"
LAST_FM_API_SECRET="<LAST FM APIのSecret>"
```

## 実行

```shell
$ uv sync
$ uv run start.py
```

動けばOK

## cronにする

(設定例: 5分毎に実行。超テキトーなのであんまり当てにしないでください)
```shell
*/5 * * * *  cd $HOME/Documents/youtube-music-scrobbler && ./.venv/bin/py
thon3 ./start.py
```

