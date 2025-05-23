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
    envsubst < letsencrypt-issuer.yaml.template > letsencrypt-issuer.yaml
    envsubst < ip-address-poo.yaml.template > ip-address-poo.yaml
    envsubst < l2-advertisement.yaml.template > l2-advertisement.yaml
    kubectl apply -f .
)
```
