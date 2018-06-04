---
id: docker-blueprint-phaser
title: Phaser Dockerサンプル
sidebar_label: Phaser Dockerサンプル
---
DAppチェーンとデモを直接実行するための、パブリックなDockerコンテナがある。必要なのはDockerのインストールのみだ。

Dockerイメージはコードがアップデートされるたびに構築されるので、常に最新となっている。

注: 下のコマンドは全ての使用可能なポートを公開するが、これはいつも必要ではないかもしれない。

## [Phaser SDKのデモ](https://github.com/loomnetwork/phaser-sdk-demo)

これはローカルのコンピュータ上で実行されており、ポート80で実行される他のwebサーバーを用いていないことを考慮して:

```bash
docker run -d -p 46656:46656 -p 46657:46657 -p 46658:46658 -p 9999:9999 loomnetwork/weave-blueprint:latest

docker run -d -p 80:3000 loomnetwork/phaser-sdk-demo:latest
```

`フェイザー-sdk-デモ` のコンテナーを実行できる同じホストで実行されている web サーバーがある場合 `-p 127.0.0.1:3000:3000` web サーバーをリバースプロキシとしてポート3000(または他の空きポート)に設定することができる。

Webブラウザにとって、`weave-blueprint`コンテナで実行されているwebsocketにアクセスできることは重要だ。

必要に応じて、docker実行のパラメータ`-p`をさらに操作することが可能である。

## [Dockerイメージ](https://hub.docker.com/r/loomnetwork/)

If you want to pull the individual images

[Loom Base](https://hub.docker.com/r/loomnetwork/loom/)

[Blueprint Contract](https://hub.docker.com/r/loomnetwork/weave-blueprint/)

[Phaser SDK UI Example](https://hub.docker.com/r/loomnetwork/phaser-sdk-demo)