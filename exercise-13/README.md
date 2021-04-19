# 13. Kubernetes Secretes and Middleware Basic Auth

 1. Created an encoded user:pass pair

```
htpasswd -nb admin password | base64 > file
```

2.  Created Kubernetes Secret

```
kubectl create secret generic admin-secret --from-file=file
```

3. Review Midlleware Basic Auth and Deploy it

## Validation

- check Kubernetes Secret

```
kubectl get secrets admin-secret -o jsonpath='{}' 
```
- check Traefik Middleware

```
kubectl get middlewares.traefik.containo.us
```
