<h1 align="center">Proxmox Networking</h1>

<p align="center">
  How virtual machines connect to segmented networks using Proxmox bridges.
</p>

---

## Overview

Virtual machines in the homelab connect to different VLAN-backed networks through Proxmox bridge interfaces.

This allows virtual workloads to be placed into the same segmented architecture as physical devices.

---

## Bridge Design

<table>
  <tr>
    <th align="left">Bridge</th>
    <th align="left">Purpose</th>
    <th align="left">Connected Network</th>
  </tr>
  <tr>
    <td><code>vmbrX</code></td>
    <td>Private infrastructure bridge</td>
    <td>Private VLAN</td>
  </tr>
  <tr>
    <td><code>vmbrX</code></td>
    <td>Public services bridge</td>
    <td>Public VLAN</td>
  </tr>
  <tr>
    <td><code>vmbrX</code></td>
    <td>Optional guest/testing bridge</td>
    <td>Guest VLAN</td>
  </tr>
</table>

---

## Example VM Placement

<table>
  <tr>
    <th align="left">VM / Service Type</th>
    <th align="left">Suggested Network</th>
  </tr>
  <tr>
    <td>Monitoring / SIEM</td>
    <td>Private VLAN</td>
  </tr>
  <tr>
    <td>Kubernetes Controller</td>
    <td>Private VLAN</td>
  </tr>
  <tr>
    <td>Nextcloud</td>
    <td>Public VLAN</td>
  </tr>
  <tr>
    <td>Portfolio Web Server</td>
    <td>Public VLAN</td>
  </tr>
</table>

---

## Benefits of This Design

<ul>
  <li>Virtual machines follow the same segmentation model as physical devices</li>
  <li>Services can be isolated by role and trust level</li>
  <li>Public-facing VMs do not need to share a bridge with sensitive infrastructure</li>
  <li>Networking remains easy to expand as the lab grows</li>
</ul>
