# Repositorio de manifests

## Descripción

Este repositorio contiene los manifests de Kubernetes para el cluster de Civo. Se divide en 3 entornos:

- Prod
- Staging
- Test

## Estructura

La estructura de carpetas es la siguiente:

```
├── README.md
├── applications
│   ├── core
│   │   ├── argo-cd
│   │   │   ├── argocd.yaml
│   │   │   └── sso-secret.encrypted.yaml
│   │   ├── cert-manager
│   │   │   ├── cert-manager.yaml
│   │   │   └── clusterissuer.yaml
│   │   ├── cluster-autoscaler
│   │   │   ├── bindings.yaml
│   │   │   ├── clusterrole.yaml
│   │   │   ├── deployment.yaml
│   │   │   ├── role.yaml
│   │   │   └── sa.yaml
│   │   ├── env-test.yaml
│   │   ├── external-dns
│   │   │   ├── cloudflare-api-token.yaml
│   │   │   └── external-dns.yaml
│   │   ├── namespace.yaml
│   │   ├── perm-manager
│   │   │   └── permission-manager.yaml
│   │   └── traefik
│   │       ├── ingressroute.yaml
│   │       └── traefik.yaml
│   ├── monitoring
│   │   ├── grafana
│   │   │   ├── dashboards.yaml
│   │   │   ├── datasources.yaml
│   │   │   ├── github-sso-secred.encrypted.yaml
│   │   │   ├── github-sso-secret.yaml
│   │   │   └── grafana-operator.yaml
│   │   ├── namespace.yaml
│   │   └── prometheus
│   │       └── kube-prometheus.yaml
│   └── permission-manager
│       ├── ingress.yaml
│       ├── kustomization.yaml
│       ├── namespace.yaml
│       └── secret.encrypted.yaml
└── environments
    ├── prod
    │   └── namespace.yaml
    ├── staging
    │   └── namespace.yaml
    └── test
        ├── namespace.yaml
        └── official-website.yaml
```

# POWERED BY [CIVO CLOUD](https://www.civo.com/)
