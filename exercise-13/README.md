# 13. Kubernetes Secretes and Middleware Basic Auth

 1. Create login credentaials using htpasswd

```
htpasswd -nBb admin password > auth
```

2.  Create Kubernetes Secret

```
kubectl create secret generic admin-secret --from-file=auth
```

Kubernetes will create base64 encoded string from the given file. That's why we don't need to encoded manually in the first step. 


3. Review Midlleware Basic Auth and Deploy it

## Validation

- check Kubernetes Secret

```
kubectl get secrets admin-secret -o jsonpath='{.data.auth}'|base64 -d 
```
- check Traefik Middleware

```
kubectl get middlewares.traefik.containo.us
```
