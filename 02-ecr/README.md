# Amazon ECRに保存したコンテナイメージをPodで使う

## ECRリポジトリの作成

このデモにはあらかじめ`eks-demo-mod5-nginx`という名前のECRリポジトリを作成する必要があります。
ECRリポジトリの作成は[こちら](https://docs.aws.amazon.com/ja_jp/AmazonECR/latest/userguide/repository-create.html)をご覧ください。

## コンテナイメージの作成

AWSマネジメントコンソールのECRリポジトリに表示されている「プッシュコマンド」をご覧ください。コマンドはこのフォルダをカレントにして実行してください。

## Podの作成

`pod.yaml`に記載されている`000000000000`を自身のAWSアカウントに変更する必要があります。

## Podへ接続する

以下のコマンドを実行すると、ローカルPCのブラウザから`localhost:8888`へアクセスするとPodのNginxへアクセスできるようになります。
```
kubectl port-forward modue05-nginx 8888:80
```