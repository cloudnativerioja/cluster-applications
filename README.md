# Repositorio de manifests

## Descripción

Este repositorio contiene los manifests de Kubernetes para el cluster de Civo. Se divide en 3 entornos:

- Prod
- Staging
- Test

## Estructura

La estructura de carpetas es la siguiente:

```
├── applications
│   ├── core
│   │   ├── argo-cd
│   │   │   └── argocd.yaml
│   │   ├── cert-manager
│   │   │   └── cert-manager.yaml
│   │   ├── cluster-autoscaler
│   │   │   ├── bindings.yaml
│   │   │   ├── clusterrole.yaml
│   │   │   ├── deployment.yaml
│   │   │   ├── role.yaml
│   │   │   └── sa.yaml
│   │   ├── env-test.yaml
│   │   ├── external-dns
│   │   │   └── external-dns.yaml
│   │   ├── metrics-server
│   │   │   └── metrics-server.yaml
│   │   ├── monitoring
│   │   │   └── prometheus-grafana.yaml
│   │   ├── namespace.yaml
│   │   ├── perm-manager
│   │   │   └── permission-manager.yaml
│   │   ├── security
│   │   │   └── security.yaml
│   │   └── traefik
│   │       ├── ingressroute.yaml
│   │       └── traefik.yaml
│   ├── monitoring
│   │   ├── grafana
│   │   │   └── grafana-operator.yaml
│   │   ├── loki
│   │   │   └── loki.yaml
│   │   ├── namespace.yaml
│   │   └── prometheus
│   │       └── kube-prometheus.yaml
│   ├── permission-manager
│   │   ├── ingress.yaml
│   │   ├── kustomization.yaml
│   │   ├── namespace.yaml
│   │   └── secret.encrypted.yaml
│   └── security
│       ├── kyverno
│       │   ├── kyverno.yaml
│       │   └── namespace.yaml
│       └── trivy
│           ├── namespace.yaml
│           └── trivy-operator.yaml
├── crds
│   └── core
│       ├── argo-cd
│       │   └── sso-secret.encrypted.yaml
│       ├── cert-manager
│       │   └── clusterissuer.yaml
│       ├── external-dns
│       │   └── cloudflare-api-token.yaml
│       ├── monitoring
│       │   └── grafana
│       │       ├── dashboards
│       │       │   ├── exporter-full-dashboard.yaml
│       │       │   ├── k3s-dashboard.yaml
│       │       │   ├── loki-logs-dashboard.yaml
│       │       │   └── trivy-vulnerabilities-dashboard.yaml
│       │       ├── datasources.yaml
│       │       └── github-sso-secred.encrypted.yaml
│       └── security
│           └── kyverno
│               └── policies
│                   ├── mutate
│                   │   └── default-labels.yaml
│                   └── validation
│                       ├── latest-tag.yaml
│                       ├── limits-requests.yaml
│                       └── no-default-ns.yaml
├── environments
│   ├── prod
│   │   └── namespace.yaml
│   ├── staging
│   │   └── namespace.yaml
│   └── test
│       ├── namespace.yaml
│       └── official-website.yaml
└── README.md
```

# POWERED BY [CIVO CLOUD](https://www.civo.com/)
