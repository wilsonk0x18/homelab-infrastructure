<h1 align="center">Proxmox Overview</h1>

<p align="center">
  High-level documentation for the primary hypervisor and the role it plays in the homelab.
</p>

---

## Overview

Proxmox VE is used as the main virtualization platform for the homelab.

It hosts a mix of Linux and Windows virtual machines that support infrastructure services, security tooling, monitoring, self-hosted applications, and experimentation.

This provides a centralized platform for compute, storage, and VM lifecycle management.

---

## Role of the Hypervisor

<table>
  <tr>
    <th align="left">Function</th>
    <th align="left">Description</th>
  </tr>
  <tr>
    <td>VM Hosting</td>
    <td>Runs infrastructure, application, and test virtual machines</td>
  </tr>
  <tr>
    <td>Network Attachment</td>
    <td>Connects VMs to segmented networks using bridge interfaces</td>
  </tr>
  <tr>
    <td>Snapshots / Recovery</td>
    <td>Supports backup and restore workflows for lab systems</td>
  </tr>
  <tr>
    <td>Resource Consolidation</td>
    <td>Allows many services to run on shared hardware rather than dedicated machines</td>
  </tr>
</table>

---

## Example VM Roles

<table>
  <tr>
    <th align="left">VM Role</th>
    <th align="left">Purpose</th>
  </tr>
  <tr>
    <td>Monitoring VM</td>
    <td>Runs Prometheus and Grafana for infrastructure visibility</td>
  </tr>
  <tr>
    <td>Security VM</td>
    <td>Runs Wazuh for monitoring and alerting</td>
  </tr>
  <tr>
    <td>Application VM</td>
    <td>Hosts self-hosted services such as personal cloud or web applications</td>
  </tr>
  <tr>
    <td>Windows Infrastructure VM</td>
    <td>Supports Active Directory and Windows administration practice</td>
  </tr>
  <tr>
    <td>Kubernetes Controller VM</td>
    <td>Hosts the K3s control plane and Rancher interface</td>
  </tr>
</table>

---

## Why Proxmox Was Chosen

<ul>
  <li>Supports both Linux and Windows workloads</li>
  <li>Provides an easy-to-manage web interface</li>
  <li>Works well for homelab-scale virtualization</li>
  <li>Integrates with backup workflows and segmented networking</li>
  <li>Makes it easy to build and rebuild systems for learning</li>
</ul>

---

## Example Workloads in This Lab

Examples from the wider lab environment include:

<ul>
  <li>Nextcloud deployed on a Proxmox VM connected to a public-facing bridge</li>
  <li>Wazuh deployed on a Proxmox VM connected to the private infrastructure network</li>
  <li>A Windows Server 2022 domain controller used for Active Directory practice</li>
</ul>

---

## Operational Benefits

Using virtualization in the homelab makes it possible to:

<ul>
  <li>Test infrastructure changes without impacting all services</li>
  <li>Run multiple operating systems on shared hardware</li>
  <li>Place VMs into different network zones</li>
  <li>Practice backup, restore, and migration workflows</li>
</ul>
