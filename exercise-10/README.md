# 10. Scaleing up / down the created deployment

## Scale up by adding more replicas to the existing deployment

```
kubectl scale deployment whoami --replicas=5
```

## Scale down the deployment

```
kubectl scale deployment whoami --replicas=2
```

## Validation

- check the deployment and replicast 

```
kubectl get deployments
kubectl get rs
```

- check the dashboard to see whether no of available replicas has been added 

