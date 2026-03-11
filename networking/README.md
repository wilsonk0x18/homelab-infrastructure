<h1 align="center">Networking Documentation</h1>

<p align="center">
  Design and documentation for the homelab network architecture, including <b>topology</b>, <b>VLAN segmentation</b>, <b>firewall boundaries</b>, <b>switching</b>, and <b>Proxmox virtual networking</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Firewall-pfSense-212121?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Switch-Juniper_EX2200-0b5cab?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Segmentation-VLANs-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Virtualization-Proxmox-blue?style=for-the-badge" />
</p>

---

## Overview

This section documents how the homelab network is designed and segmented.

The lab uses a dedicated internal firewall and managed switch to separate infrastructure into isolated networks for:

<ul>
  <li>Private infrastructure</li>
  <li>Guest devices</li>
  <li>Public-facing services</li>
</ul>

This design allows for safer experimentation with infrastructure and security tooling while keeping unrelated devices outside the monitoring boundary.

---

## Networking Documents

<table>
  <tr>
    <th align="left">Document</th>
    <th align="left">Purpose</th>
  </tr>
  <tr>
    <td><a href="./topology.md">topology.md</a></td>
    <td>High-level network layout and traffic flow</td>
  </tr>
  <tr>
    <td><a href="./vlan-design.md">vlan-design.md</a></td>
    <td>VLAN segmentation, trust boundaries, and addressing model</td>
  </tr>
  <tr>
    <td><a href="./firewall-design.md">firewall-design.md</a></td>
    <td>Why the firewall sits where it does and what it protects</td>
  </tr>
  <tr>
    <td><a href="./switching.md">switching.md</a></td>
    <td>Managed switching, trunking, and access-port design</td>
  </tr>
  <tr>
    <td><a href="./proxmox-networking.md">proxmox-networking.md</a></td>
    <td>How Proxmox bridges connect virtual machines to segmented networks</td>
  </tr>
  <tr>
    <td><a href="./segmentation-philosophy.md">segmentation-philosophy.md</a></td>
    <td>Security reasoning behind the segmented design</td>
  </tr>
</table>

---

## Diagram Reference

<p align="center">
  <img src="../architecture/network-diagram-public.png" alt="Network Diagram" width="950"/>
</p>

<p align="center">
  <i>Place the public-safe network diagram at <code>architecture/network-diagram-public.png</code></i>
</p>

---

## Core Networking Components

<table>
  <tr>
    <th align="left">Component</th>
    <th align="left">Role</th>
  </tr>
  <tr>
    <td>Apartment Router</td>
    <td>Provides upstream internet connectivity for the residence</td>
  </tr>
  <tr>
    <td>Netgate Firewall</td>
    <td>Creates a dedicated security boundary for the homelab</td>
  </tr>
  <tr>
    <td>Juniper EX2200</td>
    <td>Handles VLAN trunking and access-port segmentation</td>
  </tr>
  <tr>
    <td>Proxmox Bridges</td>
    <td>Map virtual machines to isolated VLAN-backed networks</td>
  </tr>
</table>

---

## Design Goals

<ul>
  <li>Keep homelab systems isolated from unrelated LAN devices</li>
  <li>Use VLANs to separate trust levels</li>
  <li>Allow public services to be isolated from internal infrastructure</li>
  <li>Create a realistic environment for systems and security practice</li>
</ul>
