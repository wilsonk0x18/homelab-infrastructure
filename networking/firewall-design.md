<h1 align="center">Firewall Design</h1>

<p align="center">
  Rationale and role of the internal firewall protecting the homelab environment.
</p>

---

## Overview

The firewall is intentionally placed <b>inside the existing LAN</b> rather than at the edge of the residence network.

This means the firewall protects the homelab environment specifically, rather than all devices connected to the apartment router.

---

## Why the Firewall Sits Inside the LAN

<table>
  <tr>
    <th align="left">Reason</th>
    <th align="left">Explanation</th>
  </tr>
  <tr>
    <td>Privacy</td>
    <td>Avoids monitoring or filtering unrelated traffic from other people on the shared network</td>
  </tr>
  <tr>
    <td>Control</td>
    <td>Provides full control over the homelab without requiring ownership of the whole LAN</td>
  </tr>
  <tr>
    <td>Security Practice</td>
    <td>Creates a realistic internal security boundary similar to enterprise lab or server zones</td>
  </tr>
  <tr>
    <td>Isolation</td>
    <td>Separates lab infrastructure from the rest of the residence network</td>
  </tr>
</table>

---

## Firewall Responsibilities

<ul>
  <li>Route traffic between VLANs</li>
  <li>Enforce access-control rules between segments</li>
  <li>Restrict guest network access</li>
  <li>Protect internal services from broader LAN exposure</li>
  <li>Provide a clear trust boundary for experimentation</li>
</ul>

---

## Rule Philosophy

<table>
  <tr>
    <th align="left">Segment</th>
    <th align="left">General Policy</th>
  </tr>
  <tr>
    <td>Private VLAN</td>
    <td>Trusted internal access with tightly controlled exposure outward</td>
  </tr>
  <tr>
    <td>Guest VLAN</td>
    <td>Internet access only, with restricted access to internal systems</td>
  </tr>
  <tr>
    <td>Public VLAN</td>
    <td>Limited service exposure, separated from private infrastructure</td>
  </tr>
</table>

---

## Simplified Placement Model

<pre>
Shared LAN
   ↓
Homelab Firewall
   ↓
Segmented Lab Networks
</pre>
