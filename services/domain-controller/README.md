<h1 align="center">Active Directory Domain Controller</h1>

<p align="center">
Windows Server domain environment used to manage authentication, users, and centralized network administration.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Directory-Active_Directory-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Server-Windows_Server_2022-0078D6?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Domain-lab.local-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Authentication-Kerberos-orange?style=for-the-badge"/>
</p>

---

## Overview

This system provides centralized authentication and identity management using **Microsoft Active Directory**.

The domain controller manages:

- user accounts
- authentication
- DNS services
- domain policies
- network resource access

---

## Domain Environment

<table>
<tr>
<th align="left">Setting</th>
<th align="left">Value</th>
</tr>

<tr>
<td>Domain Name</td>
<td>lab.local</td>
</tr>

<tr>
<td>Server Name</td>
<td>DC1</td>
</tr>

<tr>
<td>Operating System</td>
<td>Windows Server 2022</td>
</tr>

</table>

---

## Domain Controller Responsibilities

- user authentication
- centralized directory services
- DNS resolution
- group policy management
- domain resource access control

Client machines can join the domain and authenticate using domain credentials.

---

## Setup Documentation

➡ **[Windows Domain Controller Setup](ActiveDirectoryDomainSetupDocs)**

The full guide includes:

- Windows Server installation
- Proxmox VM configuration
- Active Directory Domain Services setup
- domain controller promotion
- Windows client domain join

This deployment demonstrates the full process of building a functional Active Directory environment within the homelab.
