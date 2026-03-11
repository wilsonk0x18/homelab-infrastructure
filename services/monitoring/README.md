<h1 align="center">Infrastructure Monitoring</h1>

<p align="center">
Monitoring stack used to collect and visualize performance metrics from homelab infrastructure.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Metrics-Prometheus-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Visualization-Grafana-F46800?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Exporter-Node_Exporter-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Host-Proxmox-grey?style=for-the-badge"/>
</p>

---

## Overview

This monitoring stack collects **system metrics from the Proxmox host and other infrastructure systems** using Prometheus.

Metrics are visualized through **Grafana dashboards**, providing insight into:

- CPU usage
- memory utilization
- disk activity
- network traffic

---

## Monitoring Architecture

<table>
<tr>
<th align="left">Component</th>
<th align="left">Role</th>
</tr>

<tr>
<td>Prometheus</td>
<td>Metrics collection and time-series database</td>
</tr>

<tr>
<td>Grafana</td>
<td>Visualization and dashboard interface</td>
</tr>

<tr>
<td>Node Exporter</td>
<td>Exports system metrics from monitored machines</td>
</tr>

</table>

---

## Data Flow

Proxmox Host<br>
     │<br>
     V<br>
Node Exporter<br>
     │<br>
     V<br>
Prometheus Server<br>
     │<br>
    V<br>
Grafana Dashboards<br>


---

## Example Metrics Collected

- CPU utilization
- memory usage
- disk activity
- network bandwidth
- system load

Grafana dashboards provide a real-time visualization of these metrics. :contentReference[oaicite:1]{index=1}

---

## Setup Documentation

➡ **[Prometheus + Grafana Setup Guide](Grafana+PrometheusDocs)**

The full guide includes:

- Prometheus installation
- Grafana installation
- Node Exporter configuration
- Prometheus scrape configuration
- Grafana dashboard import
