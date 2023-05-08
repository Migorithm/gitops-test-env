# Argo CD Demonstration
This directory contains the example materials used in the Argo CD.
In this demonstration we deploy a containerized application onto Argo CD using a GitOps approach.

## Required Tools
1.  **Docker** is used as the underlying container platform for building and running containers.  You can download and install Docker for your platform using the [official installation guide][docker-install].
2.  **kubectl** is a command line tool used to run commands against the Kubernetes cluster.  You can download and install kubectl by following the installation instructions on the [official site][kube-site].
3.  **Argo CD** is the GitOps operator that runs in the cluster and applies the example manifests.  You can download and install Argo CD by following the tools [getting started guide][argo-start].


## Commands
The following commands are used in the demonstrations.  They are provided within the readme file so that you can copy and paste them while working through the course.

1. Get Cluster Node IP with kubectl

```
kubectl get nodes -o wide
```

2. Patch a Kubernetes Deployment
```
kubectl patch deployment gitops-foundations --namespace argocd-exercise -p '{"spec":{"template":{"spec":{"containers":[{"name":"gitops-foundations","image":"[Your DockerHub ID goes here]/gitops-foundations:1.0"}]}}}}'
```

