# Kubernetes

Kubernetes is an open-source container orchestration system for automating application deployment, scaling, and management.

![kubernetes-deployment](https://github.com/rynaardb/TIL/blob/master/containerization/images/kubernetes-deployment.png?raw=true)

## Terminology

**Cluster**

A set of machines, called nodes, that run containerized applications managed by Kubernetes.

**Deployment**

An API object that manages a replicated application.

**Node**

A node is a worker machine in Kubernetes.

**Pod**

The smallest and simplest Kubernetes object. A Pod represents a set of running containers on your cluster.

**Service**

An API object that describes how to access applications, such as a set of Pods , and can describe ports and load-balancers.

**Volume**

A directory containing data, accessible to the containers in a pod .

## Set up a Kubernetes cluster on your local machine

### Prerequisites

* VirtualBox
* Docker
* Kubernetes CLI tools
* minikube

### Installation

1. Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
2. Install Xcode Developer Tools: `xcode-select --install`
3. Install Docker: https://hub.docker.com/editions/community/docker-ce-desktop-mac
4. Install minikube: `brew cask install minikube`
5. Start minikube: `minikube start`

### Using minikube

**Useful Commands**

`minikube dashboard` - starts the minikube dashboard\
`kubectl get node` - get all the nodes\
`eval $(minikube docker-env)` - creates exports for docker environment \
`minikiube docker-env` - ?
`minikube ip` - gets the IP address of the host on which minikube is running

## Creating a deployment

### Deployment yaml file (deployment.yaml)

Example of a very basic deployment:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ExampleDeployment
spec:
  selector:
    matchLabels:
      app: userServiceLabel
  replicas: 1
  template:
    spec:
      containers:
        - name: vapor-api-gateway
          imagePullPolicy: Never
          image: vapor-api-gateway:lastest
          ports:
            - containerPort: 8080
    metadata:
      labels:
        app: userServiceLabel
```
To create the deployment:

`kubectil create -f deployment.yaml`

## Exposing deployment with services

### Services yaml file (services.yaml)

```yaml
kind: Service
apiVersion: v1
metadata:
  name: User Service
spec:
  selector:
    app: userServiceLabel
  externalIPs:
    - 192.168.99.100
  type: LoadBalancer
  ports:
  - name: vapor-port
    port: 8080
    targetPort: 8080
```

To expose the service:

`kubectl apply -f services.yaml`

## Notes

* You can also create deployments using JSON
* minikube has its own docker daemon where containers will run

## Online Resources

[Trying Kubernetes for the first time video](https://www.youtube.com/watch?v=ZSuh_nNPGls)\
[Using kubectl to Create a Deploykent](https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-app/deploy-intro/)