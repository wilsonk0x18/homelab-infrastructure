<h1 align="center">Kubernetes Homelab Cluster</h1>

<p align="center">
  Documentation and demonstrations for the homelab Kubernetes cluster built with <b>K3s</b> and managed using <b>Rancher</b>.  
  This environment is used to experiment with <b>container orchestration</b>, <b>distributed workloads</b>, <b>service networking</b>, and <b>cluster management</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Orchestration-Kubernetes-326ce5?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Distribution-K3s-ffc61c?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Management-Rancher-0075a8?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Containers-Docker-2496ed?style=for-the-badge" />
</p>

---

## Overview

This section documents the Kubernetes cluster running in my homelab.  
The cluster uses **K3s**, a lightweight Kubernetes distribution, with **Rancher** providing a web-based management interface.

The goal of this project was to gain hands-on experience with:

- multi-node Kubernetes clusters
- workload scheduling
- container orchestration
- service exposure
- load balancing
- cluster visualization tools

---

## Cluster Technologies

<table>
<tr>
<th align="left">Technology</th>
<th align="left">Purpose</th>
</tr>

<tr>
<td>K3s</td>
<td>Lightweight Kubernetes distribution used for the cluster</td>
</tr>

<tr>
<td>Ubuntu Server</td>
<td>Base operating system running on each node</td>
</tr>

<tr>
<td>Rancher</td>
<td>Web-based Kubernetes management interface</td>
</tr>

<tr>
<td>Helm</td>
<td>Package manager used to install Rancher and supporting services</td>
</tr>

<tr>
<td>cert-manager</td>
<td>Handles TLS certificates required for Rancher</td>
</tr>

<tr>
<td>NodePort Services</td>
<td>Used to expose services to the homelab network</td>
</tr>

</table>

---

## What I Learned

Working with Kubernetes in a homelab environment provided practical experience with:

- container orchestration
- distributed application deployments
- pod scheduling across nodes
- service abstraction and networking
- cluster management using Rancher

This lab helped bridge the gap between **running containers locally with Docker** and **operating a distributed container platform**.

---

## Why Kubernetes?

Kubernetes allows applications to be deployed in a **scalable and fault-tolerant way** by distributing workloads across multiple machines.

Benefits include:

- automatic workload scheduling
- high availability through replicated pods
- centralized cluster management
- simplified service networking
- horizontal scaling of applications

This homelab cluster provides a platform for experimenting with these concepts in a real environment.
