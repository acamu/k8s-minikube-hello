# k8s-minikube-hello


Prerequisit

    minikube ruinning
  

Create sample application e.g. nodejs create a server.js

    var http = require('http');

    var handleRequest = function(request, response) {
      console.log('Received request for URL: ' + request.url);
      response.writeHead(200);
      response.end('Hello World!');
    };
    var www = http.createServer(handleRequest);
    www.listen(8080);


Run your application: (if nodejs installed on your system)

    node server.js


Create a Dockerfile

    FROM node:6.9.2
    EXPOSE 8080
    COPY server.js .
    CMD node server.js

Make sure you will use minikue deamon

    eval $(minikube docker-env)
    
    
Build the dockerfile (do not forget the "." at the end of the cmd line) n

    docker build -t hello-node:v1 .
    
   View deployment
   
    kubectl get deployments
   
   View pds
   
    kubectl get pods
   
   Display events
   
    kubectl get events
   
   Display condif
   
    kubectl config view
    
    
    
    
   
List the services exposed via a node port: 

    minikube service list

Create a deployment on the cluster kub

    kubectl run hello-node --image=hello-node:v1 --port=8080





[1] https://kubernetes.io/docs/tutorials/stateless-application/hello-minikube/

[2] http://www.bogotobogo.com/DevOps/DevOps-Kubernetes-1-Running-Kubernetes-Locally-via-Minikube.php

[3]
