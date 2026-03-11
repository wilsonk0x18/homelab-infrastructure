<h1 align="center">Network Topology</h1>

<p align="center">
  High-level overview of how traffic flows into and through the homelab environment.
</p>

---

## Topology Summary

The homelab does not control the entire residence network.  
Instead, it is attached to an existing LAN and protected by its own internal firewall.

This creates a dedicated boundary around the lab without requiring inspection of unrelated traffic.

---

## Logical Flow

<table>
  <tr>
    <th align="left">Stage</th>
    <th align="left">Description</th>
  </tr>
  <tr>
    <td>Internet</td>
    <td>Upstream WAN connectivity</td>
  </tr>
  <tr>
    <td>Apartment Router</td>
    <td>Main residential router for the shared LAN</td>
  </tr>
  <tr>
    <td>Homelab Firewall</td>
    <td>Dedicated pfSense firewall protecting only the homelab</td>
  </tr>
  <tr>
    <td>Managed Switch</td>
    <td>Juniper switch handling VLAN distribution</td>
  </tr>
  <tr>
    <td>Segmented Networks</td>
    <td>Private, Guest, and Public VLANs</td>
  </tr>
</table>

---

## Traffic Model

<pre>
Internet
   ↓
Apartment Router
   ↓
Netgate Firewall
   ↓
Juniper EX2200
   ↓
Private / Guest / Public VLANs
</pre>

---

## Why This Topology Was Chosen

<ul>
  <li>It avoids monitoring traffic from other people on the shared LAN</li>
  <li>It gives full control over the homelab environment</li>
  <li>It allows realistic testing of segmentation and security boundaries</li>
  <li>It behaves like a protected internal infrastructure zone</li>
</ul>
