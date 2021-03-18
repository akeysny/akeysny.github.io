---
layout: post
title: "Overview of Kubernetes"
subtitle: "Production Ready and Security in Kubernetes"
background: '/img/posts/kubernetes/background.jpeg'
---

## Kubernetes

Kubernetes is the world's most famous open-source container orchestration engine. It offers the ability to schedule and manage containers-Docker or otherwise-at scale. First, we will learn how to get a Kubernetes environment up and running, and understand the components. We will deploy a sample Kubernetes application and manage it with Kubernetes Dashboard. We will leave the most exciting part for the end; authentication and authorization.

## Getting up and running: Mac install

1. Setup all prerequisites for minikube (Docker and Virtualbox)
2. Setup and test Minikube
3. Setup and test kubectl

### Setup Prerequisities

#### Docker:

* Download links for Docker for Windows: [Windows](https://www.docker.com/docker-windows)
* Download links for Docker for Linux: [Linux](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu)
* Download links for Docker for Mac: https://www.docker.com/docker-mac

Command to test: 
{% highlight ruby %}
docker version
{% endhighlight ruby %}

#### Virtualbox

* Download link: https://www.virtualbox.org/

Command to test: `virtualbox`

### Setup Kubectl:
* Download link: https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-via-curl

Command to test: `kubectl version`