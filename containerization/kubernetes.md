# Kubernetes

Kubernetes is an open-source container orchestration system for automating application deployment, scaling, and management.

## Terminology

![kubernetes-deployment](/images/kubernetes-deployment.png)

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
* Minikube

### Installation

1. Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
2. Install Xcode Developer Tools: `xcode-select --install`
3. Install Docker: https://hub.docker.com/editions/community/docker-ce-desktop-mac
4. Install minikube: `brew cask install minikube`
5. Start minikube: `minikube start`

### Using minikube

**Commands**

`minikube dashboard` - starts the minikube dashboard
`kubectl get node` - get all the nodes

### Notes

minikube has its own docker daemon where containers will run

### Online Resources

[Trying Kubernetes for the first time video](https://www.youtube.com/watch?v=ZSuh_nNPGls)