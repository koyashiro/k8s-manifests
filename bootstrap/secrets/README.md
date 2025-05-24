# Secrets bootstrap

```sh
cp .env.example .env
```

```bash
(
    set -a
    source .env
    set +a
    envsubst < clouflare-api-token-secret.yaml.template > clouflare-api-token-secret.yaml
    envsubst < longhorn-basic-auth.yaml.template > longhorn-basic-auth.yaml
    envsubst < letsencrypt.yaml.template > letsencrypt.yaml
    envsubst < letsencrypt-staging.yaml.template > letsencrypt-staging.yaml
    envsubst < ip-address-pool.yaml.template > ip-address-pool.yaml
    kubectl apply -f .
)
```
