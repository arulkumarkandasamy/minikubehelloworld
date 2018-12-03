# Pre requitesites for running this app
## Install minikube
### Download minikube
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

### make minikube binary executable
$ chmod +x minikube

### move minikube binary to /usr/local/bin
$ sudo mv -v minikube /usr/local/bin

## Install kubectl
### Download kubectl 
$ curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.8.0/bin/linux/amd64/kubectl

### make kubectl binary executable
$ chmod +x kubectl

### move kubectl binary to /usr/local/bin
$ sudo mv -v kubectl /usr/local/bin

### start minikube
$ minikube start

# Running minikube helloworld in minikube cluster
### Clone the repo
Clone this repository in a directory

### build docker image
docker build -t DockerHub_Username/minikubehelloworld .

### Login to Docker hub
sudo docker login -u=DockerHub_Username -p=DockerHub_Password

### publish docker image to docker hub
sudo docker push DockerHub_Username/minikubehelloworld

### create kubernetes deployment with 2 replicas
kubectl create -f helloworld-deployment.yaml

## Minikube dashboard
$ minikube dashboard

### create kubernetes service
kubectl create -f helloworld-service.yaml




