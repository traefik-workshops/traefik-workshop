# 15. Enable Metrics for Prometheus

## See the changes in values yaml

There are two changes added: 

```
 - "--metrics.prometheus=true"
```

Please note, the usage of Traefik Server and the service prometheus@internal

## Create a service that expose metrics witin a cluster

```
kubectl apply -f traefik-dashboard-service.yaml
```

## Validate metrics endpoint

```
kubectl get endpoints traefik-dashboard
```

Run temporary pod to get metrics.
```
kubectl run -it --rm --image alpine -- sh
```

```
curl traefik-dashboard:9000/metrics
```

# Installing Prometheus stack using Helm 

We will install Kube-Prometheus-Stack with all components: Prometheus, Alert Manager, Grafana and Metrics exporter. 

## Add the repository

```
helm repo add prometheus-community https://github.com/prometheus-community/helm-charts
helm repo update
```

## Modify values YAML 

- Add extra chart that is needed for the example dashboard
- Add the example dashboard as JSON. You can also import the chart manually once Grafana will be deployed. 

## Install Kube Prometheus Stack

```
helm install prometheus-stack  prometheus-community/kube-prometheus-stack -f promo-stack-values.yaml
```

## Create Service Monitor that connects with Traefik Dashboard Service


```
kubectl apply -f traefik-service-monitor.yaml

```

## Create port-forward to Promethues to explore data


```
kubectl port-forward service/prometheus-stack-kube-prom-prometheus 9090:9090
```

Go to http://localhost:9090/service-discovery to see whether Traefik target has been added. 


## Create port-forward to login to the Grafana and see the sample Traefik dashboard

```
kubectl port-forward service/prometheus-stack-grafana 8080:80
```

Login credentials can be taken from Kubernetes secrets:

```
kubectl get secrets prometheus-stack-grafana -o jsonpath='{.data.admin-user}'|base64 -d
kubectl get secrets prometheus-stack-grafana -o jsonpath='{.data.admin-password}'|base64 -d
```


## Note

The following setup does not use persistence, which means once you restart the stack components all data will be lost. Review the original [values](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) file to enable data persistence for all components.


## More information

See the blog post on Traefik's website: [Capture Traefik Metrics for Apps on Kubernetes and Prometheus](https://traefik.io/blog/capture-traefik-metrics-for-apps-on-kubernetes-with-prometheus/)