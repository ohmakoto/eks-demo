# Serviceの種類毎の違いとIngress

ファイルを`00_deployment.yaml`から順番に`kubectl apply`するとデモが実行できます。

## クラスター内からServiceへアクセスする

`kubectl apply -f amzn2.yaml`でAmazonLinux2のコンテナを起動してください。
`k exec amznlinux2 -it -- /ect/bash`を実行するとコンテナにアクセスし、`curl`でクラスターIPやService名へリクエストできます。

## Ingressを使ってALBを作成する

IngressはKubernetesのオブジェクトですが、ALBを作成するには、あらかじめ[AWS Load Balancer Controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller/)を稼働させておく必要があります。Ingressマニフェストを使用する際はまずこちらを確認して[インストール](https://docs.aws.amazon.com/ja_jp/eks/latest/userguide/aws-load-balancer-controller.html)を実施してください。
