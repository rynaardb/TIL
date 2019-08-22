# Minikube

Minikube is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a Virtual Machine (VM) on your local machine

## Set up a Kubernetes cluster on your local machine (using minikube)

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

To create the deployment:

`kubectil create -f deployment.yaml`

To expose a service:

`kubectl apply -f services.yaml`

## Notes

* You can also create deployments using JSON
* minikube has its own docker daemon where containers will run