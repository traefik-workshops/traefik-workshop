# 12. Create IngressRoute for HTTPS

## Review the file and deploy it

Please note, that that file contains more Kubernets objects that will be created after applying:

- the matching rule has added condition 
- there are security headers attached to the routers, middleware headers
- there are extra SAN domains added 
- there is TLS object created 

```
kubectl apply -f ingresscrs-websecure.yaml
```

## Assign the middleware for Ingress HTTP

- modify the CRD file for HTTP and assign redirect-scheme middleware

```
kubectl apply -f ingress-web.yaml
```

## Validation:

- check whether CRD, TLSOptions and Security middleware have been created
- check HTTP -> HTTPS redirection 
