# 14. Create Ingressroute for Dashboard and API

## Review the configuration file and deploy it

```
kubectl apply -f ingresscrd-dashboard.yaml
```

Please note:
- how the matching rule has been created using `Host` nad `PathPrefix` conditions
- the usage of `TraefikService` - an abstraction layer for Service and the internal service `api@internal`

## Validation

- check whether dashboard is accessible, make sure to add trailing slash
- check wherather /api is accessible `/api/rawdata/`, `/api/version` 
