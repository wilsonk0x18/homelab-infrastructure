<h1 align="center">Kubernetes Cluster Architecture</h1>

<p align="center">
  Overview of the homelab Kubernetes cluster design including the <b>K3s control plane</b>, <b>worker nodes</b>, <b>service networking</b>, and the <b>Rancher management interface</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Cluster_Type-Multi_Node-4caf50?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Control_Plane-K3s_Controller-326ce5?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Workers-K3s_Agents-ff9800?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Networking-NodePort_Services-purple?style=for-the-badge" />
</p>

---

## Architecture Overview

The Kubernetes cluster follows a **controller / worker node architecture**.

- The **controller node** runs the Kubernetes control plane.
- **Worker nodes** run application workloads.
- **Rancher** provides a centralized interface for monitoring and managing the cluster.


---

## Core Components

<table>

<tr>
<th align="left">Component</th>
<th align="left">Function in the Lab</th>
</tr>

<tr>
<td>K3s Controller</td>
<td>Primary node responsible for cluster orchestration and API management</td>
</tr>

<tr>
<td>K3s Workers</td>
<td>Nodes that run scheduled application pods</td>
</tr>

<tr>
<td>Rancher</td>
<td>Web-based interface used to monitor and manage cluster resources</td>
</tr>

<tr>
<td>Helm</td>
<td>Used to install Rancher and other Kubernetes services</td>
</tr>

<tr>
<td>cert-manager</td>
<td>Handles TLS certificates required for Rancher</td>
</tr>

<tr>
<td>NodePort Services</td>
<td>Exposes applications to the homelab network</td>
</tr>

</table>

---

## Node Responsibilities

### Controller Node

Responsible for:

- cluster control plane
- Kubernetes API
- scheduling workloads
- storing cluster state
- Rancher management interface

### Worker Nodes

Responsible for:

- running containers
- hosting application pods
- providing compute resources for workloads

---

## Networking

Applications deployed in the cluster are exposed through **NodePort services**.

NodePort allows external access by opening a port on each node in the cluster and routing requests to available pods.

This approach works well for **internal homelab testing environments** without requiring an external load balancer.

---

## Scaling

Kubernetes allows horizontal scaling by increasing the number of pod replicas in a deployment.

Example:

| Deployment | Pods |
|-----------|------|
| nginx demo | 9 replicas |

The scheduler distributes these pods across available nodes to balance workloads.

This behavior is demonstrated in the **Load Balancing Demo**.
