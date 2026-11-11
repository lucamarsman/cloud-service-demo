Project Name: cloud-service-demo

Purpose: Demonstrating Version Control For A Cloud Project

Files Included: index.html, README.md, Dockerfile, kubernetes/deployment.yaml, kubernetes/service.yaml

Version control helps a cloud project by tracking changes to source code and configuration files. It allows a team to collaborate, revert mistakes, track bugs, and maintain a history of an application/project.

Docker is a contanerization technology that allows applications to be packaged/disributed/ran in their own isolated enviornments.
A Docker image is a read-only collection that includes everything required to run an application (source code, runtime, dependencies/libraries, configurations).
A Docker container is a running instance of a Docker image which includes a writeable layer on top of the read-only layer, which allows the application to modify/create files without altering the original image.

How to build and run this application:

    - Ensure docker is installed using "docker --version" as well as running using "docker info"
    - Clone the repository to your local machine using "git clone https://github.com/lucamarsman/cloud-service-demo.git"
    - Change to the cloned directory and run "docker build -t cloud-service-demo:1.0 ." to build the image
    - Run "docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0" to run the image in a container
    - In a browser navigate to localhost:8080 to view the running web application

Kubernetes is a container management platform which is used to automate the deployment/management/scaling of containers.
A Pod contains one or more containers and it is the smallest deployable unit in a kubernetes cluster.
A Deployment manages pods in the kubernetes cluster and ensures the desired number of instances are running at all times.
A Service provides a stable pathway to access pods over the network.

How to start Minikube and make the Docker image available:

    - Use "minikube start --driver=docker" to create a local cluster via docker
    - Use "minikube image load cloud-service-demo:1.0" to load the docker image into minikube and make it available

How to apply the Deployment and Service YAML files:

    - Use "kubectl apply -f kubernetes/deployment.yaml" to apply the deployment configuration
    - Use "kubectl apply -f kubernetes/service.yaml" to apply the service configuration

How to access the application using kubectl port-forward:

    - Use "kubectl port-forward service/cloud-service-demo 8080:80" to expose the application locally
    - Visit http://localhost:8080 in a browser to access the application
