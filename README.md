# Introduction

The goal of this tutorial is to set up a homelab on a Fedora 43 machine for preparing the **CKA exam**.  

## Useful resources

- https://kodekloud.com/
- https://killercoda.com

## What is K3s? 

K3s is a **lightweight**, easy-to-install, deploy, and manage **version** of stock **Kubernetes** (K8s).  
No, it is not a fork of Kubernetes, K3s is a certified Kubernetes distribution.

## What is K3d? 

K3d is a tool for running K3s single- and multi-node clusters in **Docker**.  
Coupling it with **kubectl** makes a fully functional homelab for preparing the CKA exam.  
This combo supports context switching between clusters to mimic exam scenarios.  

**k3d** can spin up conformant clusters in seconds via simple commands like `k3d cluster create cka-lab --servers 1 --agents 2`, covering CKA domains such as 
scheduling, RBAC (Role-Based Access Control), and storage without needing VMs.  
While **kubectl** handles all exam-required operations (e.g., kubectl apply -f, imperative edits, crictl inspections) on these clusters.  

## Limitations

k3d uses lightweight k3s, skipping full **kubeadm** bootstrapping or advanced **HA** (High-Availability) setups rarely tested in CKA.  

---

# 1. Installing Docker on Fedora 43

