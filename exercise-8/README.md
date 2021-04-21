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
- see the dashboard - please note, what is the name convention for the middleware we created.

The middleware name is created based on that pattern:
\<namespace\>-\<name-of-the-middleware\>@\<provider\> 

## Note:

- when permanent is set to true
- all GET will have a 301
- all the other requests will have a 308
