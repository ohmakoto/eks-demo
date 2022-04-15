# PodとDeploymentでコンテナを作成する

[Pod](https://kubernetes.io/ja/docs/tutorials/kubernetes-basics/explore/explore-intro/)は1つ以上のコンテナをグループにしたKubernetesのオブジェクトです。Podを宣言すると、Kubernetesでコンテナを起動できます。[Deployment](https://kubernetes.io/ja/docs/concepts/workloads/controllers/deployment/)は[ReplicaSet](https://kubernetes.io/ja/docs/concepts/workloads/controllers/replicaset/)をラップして、Pod数の維持とローリングデプロイを可能にします。

## Pod

- 作成
    - `kubectl apply -f pod.yaml`
- 確認
    - `kubectl get pods`
- 削除
    - `kubectl delete pod mod02-pod`

## Deployment

- 作成
    - `kubectl apply -f deployment.yaml`
- コンテナイメージを変更する
    - `kubectl set image deployment mod02-deployment nginx=nginx:1.21.3`
- Deploymentのコンテナ数を変更する
    - `kubectl scale deployment mod02-deployment --replicas 2`
