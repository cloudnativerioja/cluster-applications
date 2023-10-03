# Manifests repository

## Description

This repository contains all the manifests to deploy the cluster with ArgoCD.

- Prod
- Staging
- Test

## Folder structure

The folder structure is the following:

```
├── applications
│   ├── core
│   │   ├── argocd
│   │   │   └── argocd.yaml
│   │   ├── cert-manager
│   │   │   └── cert-manager.yaml
│   │   ├── cluster-autoscaler
│   │   │   ├── bindings.yaml
│   │   │   ├── clusterrole.yaml
│   │   │   ├── deployment.yaml
│   │   │   ├── role.yaml
│   │   │   └── sa.yaml
│   │   ├── env-test.yaml
│   │   ├── external-dns
│   │   │   └── external-dns.yaml
│   │   ├── metrics-server
│   │   │   └── metrics-server.yaml
│   │   ├── monitoring
│   │   │   └── prometheus-grafana.yaml
│   │   ├── perm-manager
│   │   │   └── permission-manager.yaml
│   │   ├── security
│   │   │   └── security.yaml
│   │   └── traefik
│   │       └── traefik.yaml
│   ├── monitoring
│   │   ├── grafana
│   │   │   └── grafana-operator.yaml
│   │   ├── loki
│   │   │   └── loki.yaml
│   │   ├── namespace.yaml
│   │   └── prometheus
│   │       └── kube-prometheus.yaml
│   ├── permission-manager
│   │   ├── ingress.yaml
│   │   ├── kustomization.yaml
│   │   ├── namespace.yaml
│   │   └── secret.encrypted.yaml
│   └── security
│       └── kyverno
│           ├── kyverno.yaml
│           └── namespace.yaml
├── crds
│   └── core
│       ├── argo-cd
│       │   ├── sso-secret.decrypted.yaml
│       │   └── sso-secret.encrypted.yaml
│       ├── cert-manager
│       │   └── clusterissuer.yaml
│       ├── external-dns
│       │   ├── cloudflare-api-key.decrypted.yaml
│       │   └── cloudflare-api-key.encrypted.yaml
│       ├── monitoring
│       │   └── grafana
│       │       ├── dashboards
│       │       │   ├── exporter-full-dashboard.yaml
│       │       │   ├── k3s-dashboard.yaml
│       │       │   ├── loki-logs-dashboard.yaml
│       │       │   └── trivy-vulnerabilities-dashboard.yaml
│       │       ├── datasources.yaml
│       │       ├── github-sso-secret.decrypted.yaml
│       │       └── github-sso-secret.encrypted.yaml
│       └── security
│           └── kyverno
│               └── policies
│                   ├── mutate
│                   │   └── default-labels.yaml
│                   └── validation
│                       ├── latest-tag.yaml
│                       └── no-default-ns.yaml
├── environments
│   ├── prod
│   │   └── namespace.yaml
│   ├── staging
│   │   └── namespace.yaml
│   └── test
│       ├── namespace.yaml
│       └── official-website.yaml
└── README.md
```

## How to use the same private key for all the clusters (sealed-secrets)

In order to use the same private key for all the clusters, you need to create a secret with the private key and then reference it in the `sealed-secrets-controller` deployment. The following steps will guide you through the process:

1. Create the secret with the private key and the public key:

```bash
kubectl -n core-apps create secret tls myawesomesecret --cert="public-sealed.crt" --key="private-sealed.key"
```

2. Label the secret with the `sealedsecrets.bitnami.com/sealed-secrets-key=active` label:

```bash
kubectl -n core-apps label secret myawesomesecret sealedsecrets.bitnami.com/sealed-secrets-key=active
```

3. Kill the `sealed-secrets-controller` pod:

```bash
kubectl -n core-apps delete pod -l app.kubernetes.io/name=sealed-secrets-controller
```

4. Check logs to see if the secret was loaded correctly:

```bash
kubectl -n core-apps logs -l app.kubernetes.io/name=sealed-secrets-controller
```

# POWERED BY [CIVO CLOUD](https://www.civo.com/)
