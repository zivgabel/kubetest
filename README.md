# kubetest
prerquisite:
1. minkube
   1. make sure that ingress is enabled *minikube addons enable ingress*

Step by step to make it run
1. clone this repo *git clone *
1. go into the folder *cd kubetest/*
1. Load Kubernetes Deplyments and services
   1. *kubectl apply -f hellow.yaml*
   1. *kubectl apply -f hellow2.yaml*
1. Load Ingress *apply -f ingress.yaml*
1. Look for the ip address of ingress ** 
