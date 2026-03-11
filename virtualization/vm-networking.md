<h1 align="center">VM Networking</h1>

<p align="center">
  How Proxmox virtual machines are attached to isolated network segments using bridge interfaces.
</p>

---

## Overview

Virtual machines in the homelab are connected to network segments through Proxmox bridge interfaces.

This allows VM placement to follow the same trust model used for the physical network.  
Public-facing services can live on one bridge, while internal infrastructure and management systems live on another.

---

## Why Bridge-Based Networking Matters

<ul>
  <li>Allows VMs to be placed into different VLAN-backed networks</li>
  <li>Keeps public services separated from internal systems</li>
  <li>Makes the virtual environment match the physical segmentation model</li>
  <li>Supports growth without needing separate hardware for every workload</li>
</ul>

---

## Example Bridge Roles

<table>
  <tr>
    <th align="left">Bridge</th>
    <th align="left">Purpose</th>
    <th align="left">Example Workloads</th>
  </tr>
  <tr>
    <td><code>vmbr-private</code></td>
    <td>Private infrastructure network</td>
    <td>Wazuh, monitoring, domain controller, Kubernetes controller</td>
  </tr>
  <tr>
    <td><code>vmbr-public</code></td>
    <td>Public services network</td>
    <td>Nextcloud, portfolio server, public app testing</td>
  </tr>
  <tr>
    <td><code>vmbr-guest</code></td>
    <td>Optional guest or isolated testing network</td>
    <td>Temporary endpoints, client testing, low-trust systems</td>
  </tr>
</table>

---

## Example Placement Logic

<table>
  <tr>
    <th align="left">VM Type</th>
    <th align="left">Suggested Network Placement</th>
    <th align="left">Reason</th>
  </tr>
  <tr>
    <td>Monitoring / SIEM</td>
    <td>Private bridge</td>
    <td>Should remain inside the trusted infrastructure zone</td>
  </tr>
  <tr>
    <td>Directory Services</td>
    <td>Private bridge</td>
    <td>Identity systems should stay off public segments</td>
  </tr>
  <tr>
    <td>Nextcloud</td>
    <td>Public bridge</td>
    <td>Intended for end-user access and external reachability workflows</td>
  </tr>
  <tr>
    <td>Portfolio Web Server</td>
    <td>Public bridge</td>
    <td>Public-facing service separated from internal systems</td>
  </tr>
</table>

---

## Real Examples from This Lab

The current lab documentation includes:

<ul>
  <li>A Nextcloud VM configured on <code>vmbr2</code> with a public VLAN IP assignment during Ubuntu installation.</li>
  <li>A Wazuh VM configured on <code>vmbr1</code> within the private VLAN.</li>
  <li>A Windows Server 2022 domain controller VM used for internal administration practice.</li>
</ul>
