# PodとDeploymentでコンテナを作成する

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
