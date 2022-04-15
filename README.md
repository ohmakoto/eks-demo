# EKS Demo

デモで実際に使ったマニフェストファイルを公開しています。

## 免責事項

これらのデモはお客様自身のAWSアカウントを利用します。お客様自身のAWSアカウントでプロビジョニングされたすべてのリソースのコストと管理は、お客様の責任となります。

## クラスターの作り方

デモは以下の`eksctl`コマンドで作ったクラスターで実施しています。`eksclt`コマンドのインストール方法は[こちら](https://docs.aws.amazon.com/ja_jp/eks/latest/userguide/eksctl.html)を御覧ください。

> :warning: **料金が発生**: このコマンドを実行するとAmazon EKS、Amazon EC2、Amazon VPC、AWS IAMなどのリソースが作成されますので、利用料金が発生します。</br>
> :warning: **権限に注意**: このコマンドを実行したIAMユーザー、IAMロールにKubernetesクラスタの管理者権限(`system:masters`)が付与されます。

```
eksctl create cluster \
--name LatestOcean \
--version 1.21 \
--with-oidc \
--nodegroup-name AMZN-Linux2-x86 \
--node-ami-family AmazonLinux2 \
--nodes 1 \
--nodes-min 1 \
--nodes-max 10 \
--node-volume-size 10 \
--instance-types t3.large \
--spot
```

## クラスターの削除

`eksctl delete cluster --name LatestOcean`
