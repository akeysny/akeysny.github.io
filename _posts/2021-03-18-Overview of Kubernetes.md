---
layout: post
title: "Overview of Kubernetes"
subtitle: "Production Ready and Security in Kubernetes"
background: '/img/posts/kubernetes/background.jpeg'
---

# Kubernetes

Kubernetes is the world's most famous open-source container orchestration engine. It offers the ability to schedule and manage containers-Docker or otherwise-at scale. First, we will learn how to get a Kubernetes environment up and running, and understand the components. We will deploy a sample Kubernetes application and manage it with Kubernetes Dashboard. We will leave the most exciting part for the end; authentication and authorization.

## Getting up and running: Mac install

1. Setup all prerequisites for minikube (Docker and Virtualbox)
2. Setup and test Minikube
3. Setup and test kubectl

### Setup Prerequisities

#### Docker:

* Download links for Docker for Windows: [`Windows`](https://www.docker.com/docker-windows)
* Download links for Docker for Linux: [`Linux`](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu)
* Download links for Docker for Mac: [`Mac`](https://www.docker.com/docker-mac)

Command to test: `docker version`

#### Virtualbox

* Download link: [`Virtualbox`](https://www.virtualbox.org/)

Command to test: `virtualbox`

### Setup Kubectl:
* Download link: [`Kubectl`](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-via-curl)

Command to test: `kubectl version`

### Setup Minikube:
* General Download Instructions: [`Here`](https://kubernetes.io/docs/tasks/tools/install-minikube/)
* Download link: [`Here`](https://github.com/kubernetes/minikube/releases)

Command to test: `minikube version`

### Kubernetes dashboard

Type
```
Minikube dashboard
```
![IMDb page](/img/posts/kubernetes/Picture5.png)

We see hear that it loads up the Workload Status. We can also look at Deployments here ->

This page just gives us an overview what we have running in our cluster

![IMDb page](/img/posts/kubernetes/Picture6.png)

We will look into our Deployments and we notice that we could edit our deployment if we wanted to. We could update a deployment (not recommended).

![IMDb page](/img/posts/kubernetes/Picture7.png)

We can scale a resource

![IMDb page](/img/posts/kubernetes/Picture8.png)

We will notice here that additional pods are coming up.

![IMDb page](/img/posts/kubernetes/Picture9.png)

We notice that these new pods just came up online

![IMDb page](/img/posts/kubernetes/Picture10.png)

That’s great.

You can also go inside of the pod window

![IMDb page](/img/posts/kubernetes/Picture11.png)



