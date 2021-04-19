# 9. Update the Ingress definition by adding the annotation

## Review the file and deploy it. 

```
kubectl apply -f ingress-web.yaml
```

Note, that middleware is assigned to the web entrypoint that referes to HTTP

## Validation


- check whether annotation has been added to the ingress

```
kubectl describe ing whoami
```

- use curl to check whether redirection works correcly