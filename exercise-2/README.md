# 2. First look on to Traefik Dashboard

We will use port-forwarding to forward connection directly to the pod where Traefik is running. We will use selector to match the pod name.

```
kubectl port-forward $(kubectl get pods --selector "app.kubernetes.io/name=traefik" --output=name) 9000:9000
```

Please note the port 9000 that is one of the created entrypoints 

## Explore dashboard

Go to http://localhost:9000/dashboard/ and you should get dashboard. 

