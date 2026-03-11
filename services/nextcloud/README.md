<h1 align="center">Nextcloud Personal Cloud</h1>

<p align="center">
Self-hosted cloud storage platform providing secure file synchronization, sharing, and remote access for my homelab environment.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Service-Nextcloud-0082c9?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/OS-Ubuntu_Server-77216f?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Access-Tunnelto-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Storage-Self_Hosted-blue?style=for-the-badge"/>
</p>

---

## Overview

Nextcloud provides a **self-hosted alternative to cloud storage services** like Google Drive or Dropbox.  
This deployment runs inside a **Proxmox VM** and allows secure file storage and sharing across devices.

The instance is made remotely accessible using **Tunnelto**, which creates a secure public tunnel to the server.

---

## Service Details

<table>
<tr>
<th align="left">Component</th>
<th align="left">Description</th>
</tr>

<tr>
<td>Platform</td>
<td>Nextcloud Snap Package</td>
</tr>

<tr>
<td>Operating System</td>
<td>Ubuntu Server 22.04</td>
</tr>

<tr>
<td>Hosting</td>
<td>Proxmox Virtual Machine</td>
</tr>

<tr>
<td>Network</td>
<td>Public VLAN</td>
</tr>

<tr>
<td>Remote Access</td>
<td>Tunnelto HTTPS Tunnel</td>
</tr>

</table>

---

## VM Specifications

<table>
<tr>
<th align="left">Resource</th>
<th align="left">Allocation</th>
</tr>

<tr>
<td>CPU</td>
<td>2 vCPUs</td>
</tr>

<tr>
<td>Memory</td>
<td>4 GB</td>
</tr>

<tr>
<td>Storage</td>
<td>1 TB</td>
</tr>

</table>

---

## Key Features

- Private cloud storage
- File sharing and collaboration
- Mobile and desktop sync clients
- Web-based file access
- Secure remote access via Tunnelto

---

## Setup Documentation

The full installation and configuration process is documented here:

➡ **[Nextcloud Setup Guide](NextcloudDocs)**

This guide covers:

- Proxmox VM configuration
- Ubuntu installation
- Nextcloud snap deployment
- Tunnelto remote access configuration
- Persistent tunnel service setup

The system ultimately exposes the Nextcloud instance through a public tunnel domain for remote access. 
