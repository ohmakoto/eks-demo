# ストレージをPodにマウントする

EBSを扱いますので、あらかじめ[Amazon EBS CSIドライバー](https://docs.aws.amazon.com/ja_jp/eks/latest/userguide/ebs-csi.html){target=_blank}が使える状態にしておいてください。

## 既存のEBSボリュームをPodにマウントする

1. 何か適当なEBSボリュームを作成する
2. pv.yamlに記載しているPersistentVolumeの`volumeHandle`に作成したEBSボリュームのIDを設定する
3. `kubectl apply -f pv.yaml`を行う
4. `kubectl apply -f pvc.yaml`を行う
5. `kubectl apply -f pod.yaml`を行う

## EBSボリュームを動的に作成する

1. `kubectl apply -f storageclass.yaml`を行う
2. `kubectl apply -f pvc-dynamic.yaml`を行う
3. pod.yamlの`claimName`を`mod8-pvc-30g`に書き換える
4. `kubectl apply -f pod.yaml`を行う