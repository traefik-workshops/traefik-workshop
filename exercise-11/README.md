# 11. Kubernetes IngressRouter for HTTP

## Review the IngressRouter CRD and deploy it

We will create Ingressroute for the same WHOAMI application but we will change the URL to access the application. 

```
kubectl apply -f ingresscrd-web.yaml
```

## Validation

- check whether new CRD has been created

```
kubectl get ingressroutes.traefik.containo.us

```
- check Traefik dashboard to see whether IngressRoute has been created
