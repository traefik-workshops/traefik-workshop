# 1. Installing Traefik using official Helm Chart

## Add Traefik's Helm Chart

```
helm repo add traefik https://helm.traefik.io/traefik
```

## Update the chart repository repo

```
helm repo update
```

## Install Traefik with default values

```
helm install traefik traefik/traefik
```


## Validate the installation

Traefik will be installed in the current namespace based on the Kubernetes context settings. 

Check Helm Releases, please note the chart and the Traefik version. 
```
helm ls
```

Check what pods have been created:

```
kubectl get pods
```

Check what services have been added by Traefik:

```
kubectl get svc/traefik
```


Check what other objects have been created:

```
kubectl get all -l"app.kubernetes.io/instance=traefik"
```

Describe the Traefik pod to see CLI arguments and other depoyment specific parameters:

```
kubectl describe pod <TRAEFIK-POD-NAME>
```

## Update DNS entry for your domain

Get the IP address that has been assigned - EXTERNAL-IP - field and update your DNS by creating wild card entry: `*.example.com` pointing to the EXTERNAL-IP. 

## Review the values that can be customized during Traefik instalation; 

[https://github.com/traefik/traefik-helm-chart/blob/master/traefik/values.yaml](https://github.com/traefik/traefik-helm-chart/blob/master/traefik/values.yaml)

