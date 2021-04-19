# 6. Deploy Traefik with the new configuration

```
helm upgrade traefik traefik/traefik -f values.yaml
```

## Validation

Check Helm releases

```
helm ls
```

Describe the Traefik pod

```
kubectl describe pod <TRAEFIK-POD>
```

Descibe the pvc:
```
kubectl describe pvc
```


