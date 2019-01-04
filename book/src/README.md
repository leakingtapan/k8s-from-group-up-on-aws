# Kubernetes from the Ground Up
Learning Kubernetes and setting it up manually by yourself is not an easy task. This tutorial aims at making this process smooth and helps you go through setting up kubernetes cluster from the ground up on AWS. This is inspired by [Kamal's blog post](http://kamalmarhubi.com/blog/2015/08/27/what-even-is-a-kubelet/) blog. However, it was based off Kuberentes version 1.10.3 which is pretty old. And it is missing a lot of latest components such as Container Networking Interface (CNI) plugin, Container Runtime Interface (CRI), Container Storage Interface (CSI) driver etc.

The goal of this tutorial is to provide a smooth learning curve to help you to understand Kubernetes in a practical but not that hard way. Since kubernetes is already complicated, I am not going to make it even harder for new beginners. And learning should always be an enjoying process.

## Target Audience
The target audience of this tutorial is for people who is looking for learning setting up kubernetes cluster by hand and its best practises. If you want to use a automated solution, you can use [EKS](https://aws.amazon.com/eks/) which is a AWS managed service or [Kops](https://github.com/kubernetes/kops) which is a community supported tool.

## Prerequisites
1. Basic understanding of Kubernetes high level components such as API server, controller manager, scheduler and kubelet.
1. Familiar with Kubernetes basic concepts such as Pod, Services, Controller Pattern.
1. Familiar with AWS services including EC2, VPC, ELB.

You can go through Kubernetes [onboarding tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/) and [AWS documentation](https://docs.aws.amazon.com/index.html#lang/en_us) to get yourself familiar with those concepts.

# Kubernetes Architecture
//TODO: insert image

# Modules
1. [Single Node Cluster](SingleNode.md)
1. [References](References.md)


