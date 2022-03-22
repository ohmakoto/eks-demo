# IAMロールをPodに渡す

あらかじめServiceAccountを作成する必要があります。

> :warning: **権限管理**: このコマンドを実行するとAmazonS3FullAccessポリシーがアタッチされたIAMロールが作成されます。

```
eksctl create iamserviceaccount \
    --name module09-s3 \
    --namespace default \
    --cluster LatestOcean \
    --attach-policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess \
    --approve
```

## ServiceAccountの削除

下記コマンドを実行するとServiceAccountとIAMロールが削除されます。
```
eksctl delete iamserviceaccount \
    --name module09-s3 \
    --namespace default \
    --cluster LatestOcean
```