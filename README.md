# devops-practice
practice the devops fundamentals

# DOCKER: https://www.youtube.com/watch?v=pg19Z8LL06w&list=PLu4c8cEM1tWvz5D5MN76-LgaosBSORiYL&index=7 

# Pull the image from docker hub
docker pull image:tag

# Run the contianer for the image
docker run image:tag

# Run the container in detached mode
docker run -d image:tag

# Run the container with port mapping
docker run -d -p <localhost port>:<container port> image:tag

# Run the container with port mapping and particular name
docker run --name <container_name> -d -p <localhost port>:<container port> image:tag

# Run the container with port mapping and particular name and go into interactive mode(terminal of the docker or inside the container)
docker run -it --name <container_name> -d -p <localhost port>:<container port> image:tag bash or sh.

# Check all ruuning containers
docker ps

# Check all running and stopped containers
docker ps -a

# Stop the container
docker stop <container_id/name>

# Start the previously created stopped container
docker start <container_id/name>

# Remove the stopped container
docker rm <container_id/name>

# Remove the running container forcefully
docker rm -f <container_id/name>

# Build the Image from fockerfile
docker build -t <tag_name>:<version> <location_of_dockerfile>

# Check the images available
docker images

# Kubernetes: https://www.youtube.com/watch?v=s_o8dwzRlu4&list=PLu4c8cEM1tWvz5D5MN76-LgaosBSORiYL&index=7

### Repository for the K8s in 1 hour video

#### K8s manifest files 
* mongo-config.yaml
* mongo-secret.yaml
* mongo.yaml
* webapp.yaml

#### K8s commands

##### start Minikube and check status
    minikube start --vm-driver=hyperkit 
    minikube status

##### get minikube node's ip address
    minikube ip

##### get basic info about k8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

##### get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

##### get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs
    kubectl logs {pod-name}
    
##### stop your Minikube cluster
    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />

#### Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour

