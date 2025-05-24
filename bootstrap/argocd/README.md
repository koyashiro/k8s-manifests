# ArgoCD bootstrap

```sh
helmfile apply
kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

```sh
(
 set -a
 source .env
 set +a
 helmfile apply
)
```
