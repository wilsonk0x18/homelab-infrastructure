<h1 align="center">Virtualization Documentation</h1>

<p align="center">
  Documentation for the homelab virtualization layer, including <b>Proxmox VE</b>, <b>virtual machine design</b>, <b>network attachment</b>, and <b>backup strategy</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Hypervisor-Proxmox-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Backups-Proxmox_Backup_Server-6a1b9a?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Networking-VM_Bridges-00897b?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Workloads-Linux_%2B_Windows-455a64?style=for-the-badge" />
</p>

---

## Overview

This section documents the virtualization layer of the homelab.

Proxmox VE is used as the primary hypervisor for running infrastructure services, security tooling, application servers, and test environments.  
Virtual machines are attached to segmented networks using Proxmox bridges, allowing workloads to be placed into isolated trust zones.

---

## Virtualization Documents

<table>
  <tr>
    <th align="left">Document</th>
    <th align="left">Purpose</th>
  </tr>
  <tr>
    <td><a href="./proxmox-overview.md">proxmox-overview.md</a></td>
    <td>High-level view of the Proxmox host, VM roles, and workload placement</td>
  </tr>
  <tr>
    <td><a href="./proxmox-backup.md">proxmox-backup.md</a></td>
    <td>Backup strategy, Proxmox Backup Server integration, and recovery planning</td>
  </tr>
  <tr>
    <td><a href="./vm-networking.md">vm-networking.md</a></td>
    <td>How Proxmox bridges map VMs into private and public network segments</td>
  </tr>
</table>

---

## Virtualization Goals

<ul>
  <li>Consolidate multiple services onto centralized hardware</li>
  <li>Separate workloads by purpose and trust level</li>
  <li>Make infrastructure easy to back up, restore, and expand</li>
  <li>Provide a flexible platform for both production-style services and lab experimentation</li>
</ul>

---

## Example Workload Types

<table>
  <tr>
    <th align="left">Category</th>
    <th align="left">Examples</th>
  </tr>
  <tr>
    <td>Infrastructure</td>
    <td>Domain controller, monitoring VM, backup services</td>
  </tr>
  <tr>
    <td>Security</td>
    <td>Wazuh server, internal logging systems, test endpoints</td>
  </tr>
  <tr>
    <td>Applications</td>
    <td>Nextcloud, portfolio web server, internal admin services</td>
  </tr>
  <tr>
    <td>Orchestration</td>
    <td>Kubernetes controller VM and cluster-related services</td>
  </tr>
</table>

---

## Design Philosophy

The virtualization layer is treated like the core compute platform of the lab.

Instead of running all services directly on separate physical hardware, Proxmox allows:

<ul>
  <li>fast provisioning of new systems</li>
  <li>network-aware placement of workloads</li>
  <li>simpler snapshots and backups</li>
  <li>safe testing of Windows and Linux environments</li>
</ul>
