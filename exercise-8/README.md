# 8. Create Traefik Middleware with RedirectScheme

## Review the middleware source file and apply it

```
kubectl apply -f redirect-scheme.yaml
```

## Validation

- check whethet object has been created

```
kubectl get middlewares.traefik.containo.us 
```