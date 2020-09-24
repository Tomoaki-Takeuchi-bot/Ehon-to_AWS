## EKS クラスターへの API アプリケーションデプロイ

- Namespace の作成
- kubeconfig への Namespace の反映
- データベース接続用 Secret の登録
- API アプリケーションのデプロイ
- API アプリケーションの公開

## 実行手順

- Namespace の作成 (create_namespace.yaml)
- kubeconfig への Namespace の反映

```
kubectl apply -f create_namespace.yaml
```

- データベース接続用 Secret の登録

```
DB_URL=postgresql://**RDSエンドポイントアドレス**/myworddb \
DB_PASSWORD='アプリケーション用データベースのパスワード' \
envsubst < db_config_k8s.yaml | \
kubectl apply -f -
```

# WIP

- API アプリケーションのデプロイ (WIP)

```
ECR_HOST=**ECR URIアドレス** \
envsubst < deployment_backend-app_k8s.yaml | \
kubectl apply -f -
```

- API アプリケーションの公開
