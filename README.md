# Nuxt.jsサンプル

## 構成
- node 8.11.3
- yarn

## ローカル環境構築

### 前提条件
- macOS
- Homebrew
- git ( `$ brew install git` )
- docker for mac ( `$ brew cask install docker` )

### サーバ起動
```bash
# ワークス−ペース作成 (任意フォルダ)
$ mkdir -p ~/workspace/nuxt.js-sample/
$ cd ~/workspace/nuxt.js-sample/

# コード配置
$ git clone git@github.com:reflet/nuxt.js-sample.git .

# dockerイメージを構築する
$ docker-compose build

# パッケージをインストールする
$ docker-compose run nuxtjs yarn install

# コンテナを起動する
$ docker-compose up -d
```

ブラウザを起動して動作確認する
```bash
$ open http://192.168.99.100:3000/
```
※ `192.168.99.100`は、環境によって異なることがあります。

### 日々の作業
```bash
# サーバの状態確認
$ docker-compose ps

# サーバのログ確認 (最新10件を継続して監視 - ctrl + c で確認終了)
$ docker-compose logs -f --tail 10 go 

# サーバ停止
$ docker-compose stop

# サーバ開始
$ docker-compose start

# サーバ破棄 (コンテナのみ)
$ docker-compose down

# サーバ破棄 (コンテナ＋ボリューム)
$ docker-compose down -v
```

### nuxt.jsプロジェクト作成方法
「docker/nuxtjs/src/app」のプロジェクトを作成する場合のコマンドです。

```bash
$ docker-compose run nuxtjs bash -c "cd /src && vue init nuxt-community/starter-template app"
```
