# 15. Enable Metrics for Prometheus

## See the changes in values yaml

There are two changes added: 

```
 - "--metrics.prometheus=true"
 - "--metrics.prometheus.manualrouting=true"
```

## Ingressroute for the dedicated endpoint for metrics


```
kubectl apply -f ingresscrd-metrics.yaml
```

Please note, the usage of Traefik Server and the service prometheus@internal

