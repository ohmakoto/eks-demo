# Serviceの種類毎の違いとIngress

ファイルを`00_deployment.yaml`から順番に`kubectl apply`するとデモが実行できます。

## クラスター内からServiceへアクセスする

`kubectl apply -f amzn2.yaml`でAmazonLinux2のコンテナを起動してください。
`k exec amznlinux2 -it -- /ect/bash`を実行するとコンテナにアクセスし、`curl`でクラスターIPやService名へリクエストできます。
