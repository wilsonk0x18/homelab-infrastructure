<h1 align="center">VLAN Design</h1>

<p align="center">
  Network segmentation strategy for isolating services by purpose and trust level.
</p>

---

## VLAN Overview

The homelab is divided into multiple VLANs so that workloads can be separated based on their function and risk profile.

<table>
  <tr>
    <th align="left">VLAN</th>
    <th align="left">Example Subnet</th>
    <th align="left">Purpose</th>
    <th align="left">Trust Level</th>
  </tr>
  <tr>
    <td><b>VLAN 20</b></td>
    <td><code>192.168.X.0/24</code></td>
    <td>Private infrastructure</td>
    <td>High</td>
  </tr>
  <tr>
    <td><b>VLAN 30</b></td>
    <td><code>192.168.X.0/24</code></td>
    <td>Guest devices</td>
    <td>Low</td>
  </tr>
  <tr>
    <td><b>VLAN 40</b></td>
    <td><code>192.168.X.0/24</code></td>
    <td>Public-facing services</td>
    <td>Medium</td>
  </tr>
</table>

---

## Segment Breakdown

### Private VLAN

Used for internal infrastructure and services that should not be directly reachable by untrusted devices.

Examples:

<ul>
  <li>Proxmox management and internal VMs</li>
  <li>Kubernetes controller and worker nodes</li>
  <li>Monitoring and logging systems</li>
  <li>Internal admin services</li>
</ul>

### Guest VLAN

Used for untrusted or temporary devices that should only have limited network access.

Examples:

<ul>
  <li>Guest wireless clients</li>
  <li>Temporary devices</li>
  <li>Devices that should not reach core infrastructure</li>
</ul>

### Public VLAN

Used for services intentionally exposed to users or external access paths.

Examples:

<ul>
  <li>Personal cloud services</li>
  <li>Portfolio web hosting</li>
  <li>Public-facing application testing</li>
</ul>

---

## Design Goals

<ul>
  <li>Reduce the attack surface of internal systems</li>
  <li>Keep guest devices separated from infrastructure</li>
  <li>Prevent public services from residing on the same segment as sensitive systems</li>
  <li>Mirror a simplified enterprise network design</li>
</ul>
  <li><code>&lt;private-gateway&gt;</code></li>
  <li><code>&lt;public-service-ip&gt;</code></li>
</ul>
