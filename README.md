# kubetest
## Configuration
prerquisite:
1. minkube
   1. make sure that ingress is enabled *minikube addons enable ingress*

Step by step to make it run
1. Clone this repo *git clone *
1. Go into the folder *cd kubetest/*
1. Create the ingress tls secret
   1. *cd tls*
   1. *kubectl create secret tls hellowdemo --key key.pem --cert cert.pem*
   1. *cd ..*
1. Load Kubernetes Deplyments and services
   1. *kubectl apply -f hellow.yaml*
   1. *kubectl apply -f hellow2.yaml*
1. Load Ingress *apply -f ingress.yaml*
1. Look for the ip address of ingress *kubectl get ingress* <br/>
   hellow-ingress   <none>   hellowdemo.com   **192.168.49.2**   80, 443   5m56s
1. as root add this line to /etc/hosts<br/>
   `192.168.49.2 hellowdemo.com`
## Testing
   *curl --insecure https://hellowdemo.com/routea*<br/>
   should output something like<br/>
   `Hello, world!<br/>
Version: 1.0.0<br/>
Hostname: hellow-deployment-d6d8df5bf-6zn7h<br/><br/>`
 *curl --insecure https://hellowdemo.com/routeb*<br/>
   should output something like<br/>
   Hello, world!<br/>
Version: 2.0.0<br/>
Hostname: hellow-deployment-2-66c9f75c8d-qvgmq<br/>'
