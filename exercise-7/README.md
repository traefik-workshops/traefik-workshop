# 7. Created Kubernetes Ingress (HTTPS)

## Review and deploy Kubernetes Ingress object, 

```
kubectl apply -f ingress-websecure.yaml
```

Note, the annotation has been added such as Entrypoint and Certifcate Resolvers 


## Validation

- check whether ingress has been created

```
kubectl get ing -A
kubectl describe ing / <ingress-name> 
```
- check Traefik logs to see whether certificate has been issued

```
kubectl logs traefik-pod -f
```
 
- go to inside to the container to see whether file has been created

```
kubctl exec -it <TRAEFIK_POD> sh
```

- validate the application using curl