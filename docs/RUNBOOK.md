# Runbook

## Service

- Name: `jest-api`
- Team: `Payments`
- Owner: `mooref068@gmail.com`
- Cost center: `payments`

## First Checks

```bash
kubectl get rollout jest-api -n jest-api-dev
kubectl get pods -l app.kubernetes.io/name=jest-api -n jest-api-dev
kubectl logs -l app.kubernetes.io/name=jest-api -n jest-api-dev
```

## Health

```bash
curl https://jest-api.dev.platform.ohanyere.internal/healthz
curl https://jest-api.dev.platform.ohanyere.internal/readyz
curl https://jest-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo jest-api -n jest-api-dev
```

Escalate to `Payments` through `mooref068@gmail.com` if rollback does not restore service.
