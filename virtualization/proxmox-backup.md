<h1 align="center">Proxmox Backup Strategy</h1>

<p align="center">
  Backup and recovery design for virtual machines running in the homelab environment.
</p>

---

## Overview

Backups are a critical part of the virtualization layer.

The homelab uses Proxmox Backup Server as a centralized destination for VM backups, allowing important systems to be backed up, verified, and restored when needed. The documented workflow includes installing Proxmox Backup Server, creating a datastore, creating a backup user, connecting Proxmox VE to the backup server, and running scheduled or manual VM backups.

---

## Backup Goals

<ul>
  <li>Protect important virtual machines from host failure or accidental changes</li>
  <li>Allow fast recovery of infrastructure services</li>
  <li>Centralize backup storage</li>
  <li>Make restores repeatable and easy to document</li>
</ul>

---

## Backup Architecture

<table>
  <tr>
    <th align="left">Component</th>
    <th align="left">Purpose</th>
  </tr>
  <tr>
    <td>Proxmox VE Host</td>
    <td>Runs virtual machines and initiates backup jobs</td>
  </tr>
  <tr>
    <td>Proxmox Backup Server</td>
    <td>Receives, stores, and manages backup data</td>
  </tr>
  <tr>
    <td>Datastore</td>
    <td>Logical location where VM backups are stored</td>
  </tr>
  <tr>
    <td>Backup Jobs</td>
    <td>Scheduled tasks for protecting selected VMs</td>
  </tr>
</table>

---

## Documented Backup Workflow

The current backup documentation covers the following sequence:

<ol>
  <li>Install Proxmox Backup Server</li>
  <li>Configure networking and package repositories</li>
  <li>Prepare backup disks and create storage pool</li>
  <li>Create a datastore for VM backups</li>
  <li>Create a dedicated backup user and assign permissions</li>
  <li>Connect the Proxmox VE node to PBS</li>
  <li>Create backup jobs and validate restores</li>
</ol>

---

## Recommended Backup Scope

<table>
  <tr>
    <th align="left">Workload Type</th>
    <th align="left">Suggested Protection Level</th>
  </tr>
  <tr>
    <td>Infrastructure VMs</td>
    <td>High priority, scheduled backups</td>
  </tr>
  <tr>
    <td>Security / Monitoring VMs</td>
    <td>High priority, scheduled backups</td>
  </tr>
  <tr>
    <td>Public Application VMs</td>
    <td>High priority if hosting important data or services</td>
  </tr>
  <tr>
    <td>Temporary Test VMs</td>
    <td>Optional, depending on purpose</td>
  </tr>
</table>

---

## Recovery Philosophy

A backup strategy is only useful if recovery is practical.

For this reason, the lab focuses on:

<ul>
  <li>keeping backups centralized</li>
  <li>testing manual backup jobs</li>
  <li>maintaining enough documentation to reconnect storage and restore key systems</li>
  <li>prioritizing important infrastructure first</li>
</ul>

---

## Example Recovery Priorities

<table>
  <tr>
    <th align="left">Priority</th>
    <th align="left">Examples</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Core infrastructure, identity, firewall-adjacent support services</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Monitoring and security tooling</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Application services such as cloud storage and web apps</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Temporary or experimental systems</td>
  </tr>
