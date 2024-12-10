# Setting Up Minikube with Docker and Angular

This guide provides instructions to set up a Minikube cluster, build and run an Angular application using Docker, and manage deployments using Kubernetes.

## Prerequisites
1. **Install Minikube**
   Follow the official [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/).

2. **Install Docker**  
   Refer to the [Docker Installation Guide](https://docs.docker.com/get-docker/).

3. **Configure `/etc/hosts`**  
   Add the following entry to your `/etc/hosts` file:  
   ```plaintext
   <YASH_IP> yash

## Imp Commands

**Minikubes Commands**

minikube start

eval $(minikube docker-env)

**Docker Commands**

docker build -t angular .

docker run --name angular -p 80:80 angular

**kubectl Commands**

kubectl apply -f deployment.yaml

minikube service angular-service

To enable the NGINX Ingress controller, run the following command:
minikube addons enable ingress

It can take up to a minute before you see these pods running OK.

kubectl get pods -n ingress-nginx

**check your application**

curl yash.com --resolve yash.com:80:192.168.49.2

