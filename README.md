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
│   └── core
│       ├── cert-manager
│       │   ├── cert-manager.yaml
│       │   ├── cloudflare-api-token.yaml
│       │   └── clusterissuer.yaml
│       ├── env-test.yaml
│       ├── external-dns
│       │   └── external-dns.yaml
│       └── namespace.yaml
├── environments
│   ├── prod
│   │   └── namespace.yaml
│   ├── staging
│   │   └── namespace.yaml
│   └── test
│       └── namespace.yaml
└── README.md
```
