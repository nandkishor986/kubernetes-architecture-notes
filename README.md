# Kubernetes Architecture – Detailed Notes

## Overview

This document explains Kubernetes architecture in a simplified and structured manner.

Kubernetes is divided into:

- Control Plane
- Data Plane (Worker Nodes)

---

## Control Plane Components

### API Server
Entry point to the cluster. All requests go through this component.

### Scheduler
Selects appropriate node for Pod placement.

### Controller Manager
Maintains desired state (ReplicaSets, Deployments, etc.).

### etcd
Key-value store that holds cluster state.

### Cloud Controller Manager
Integrates Kubernetes with cloud providers.

---

## Data Plane Components

### kubelet
Ensures containers are running on worker nodes.

### kube-proxy
Manages networking and service routing.

### Container Runtime
Executes containers (containerd / CRI-O).

---

## Pod Creation Flow

1. User sends request via kubectl
2. API Server validates and stores in etcd
3. Scheduler selects node
4. kubelet receives instruction
5. Container runtime starts container
6. kube-proxy configures networking

---

## Diagrams

### Architecture Diagram: 

![Architecture](./diagrams/architecture.png)

### Pod Creation Flow: 

![Pod Flow](./diagrams/pod-creation-flow.png)

