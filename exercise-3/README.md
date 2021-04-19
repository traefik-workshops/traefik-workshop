# 3. Deploying test application 

## Review and deploy the WHOAMI deployment 

```
kubectl apply -f whoami-deployment.yaml
```

## Review and deply service

```
kubectl apply -f whoami-service.yaml
```

## Validate the configuration

Check deployment:

```
kubectl describe deployment whoami
```

Check service:

```
kubectl describe svc whoami
```

Check created endpoints:

```
kubectl get endpoints
kubectl describe endpoints whoami
```

