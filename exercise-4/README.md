# 4. Create Kubernetes Ingress to expose WHOAMI app through HTTP

## Review and deploy the Ingress object

```
kubectl apply -f ingress-web.yaml
```

Note the Traefk annotation that has been added.

## Validate

Check ingresses

```
kubectl get ing -A 
```

See what has been changed in the dashboard. 
