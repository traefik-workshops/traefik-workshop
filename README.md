# Getting started with Traefik on Kubernetes
# Traefik Workshop #1

## Prerequisities

You need to have Kubernetes cluster that you can connect to, Helm3 installed and a domain that points to the external IP address of the cluster. 

## A quick deployment of Kubernetes cluster

K3D is a lightweight wrapper to run multi-node cluster. It will spin up K3S under in docker. Currently, it comes with Traefik v1, that's why we need to set arguments to disable Traefik while provision cluster for the workshop purposes. 

One can use the following command to setup a cluster:

```bash
k3d cluster create workshop \
--k3s-server-arg "--disable=traefik"  \
-p "80:80@loadbalancer" \
-p "443:443@loadbalancer" \
--agents 2
```

It will create the cluster with two worker nodes and expose the port 80 and 443. It is enough to go through the exercises below. 

## Installing Helm

Helm is the package manager for Kubernetes. Here is the link to [the official Helm docs](https://helm.sh/docs/intro/install/) to guide how to install Helm3+ in your local environment. 

Installing Traefik through package manger will run a preconfigured Traefik instance. It is one of the recommended approaches.
You can start exploring Traefik and focus on its features. There is still option to deploy it manually on your Kubernets cluster. 

# The agenda of the hands on workshops 

1. [Installing Traefik Proxy](exercise-1)
1. [Traefik Dashboard](exercise-2)
1. [Deploying test application on Kubernetes](exercise-3)
1. [Creating Kubernetes Ingress HTTP](exercise-4)
1. [Adding extra configuration to values.yaml](exercise-5)
1. [Deploying Traefik with the new configuration](exercise-6)
1. [Creating Kubernetes Ingress HTTPS](exercise-7)
1. [Creating Redirectscheme middleware](exercise-8)
1. [Assigning Middleware to the Kubernetes Ingress HTTP](exercise-9)
1. [Scaling up / down the application](exercise-10)
1. [Creating Kubernets CRD (HTTP)](exercise-11)
1. [Creating Kubernetes CRD (HTTPS)](exercise-12)
1. [Creating Basic Auth Middleware with Kubernetes Secrets](exercise-13)
1. [Kubernetes CRD for Dashboard](exercise-14)
1. [Enabling metrics endpoint](exercise-15)
   1. [Installing Prometheus Stack](exercise-15#151-installing-prometheus-stack-using-helm)
