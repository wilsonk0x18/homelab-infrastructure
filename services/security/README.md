<h1 align="center">Wazuh Security Monitoring</h1>

<p align="center">
Host-based intrusion detection and security monitoring platform used to analyze logs, detect threats, and monitor system activity.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/SIEM-Wazuh-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Detection-HIDS-red?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Agents-Windows-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Logging-Elastic_Stack-black?style=for-the-badge"/>
</p>

---

## Overview

Wazuh provides centralized security monitoring for systems in the homelab environment.

The platform collects logs and security telemetry from monitored hosts and provides detection capabilities such as:

- intrusion detection
- file integrity monitoring
- log analysis
- security alerting

---

## Architecture

<table>
<tr>
<th align="left">Component</th>
<th align="left">Purpose</th>
</tr>

<tr>
<td>Wazuh Manager</td>
<td>Processes logs and applies security detection rules</td>
</tr>

<tr>
<td>Elasticsearch</td>
<td>Stores security events and telemetry data</td>
</tr>

<tr>
<td>Kibana Dashboard</td>
<td>Visualization interface for alerts and monitoring</td>
</tr>

<tr>
<td>Windows Agents</td>
<td>Collect logs and send telemetry to the Wazuh server</td>
</tr>

</table>

---

## Lab Deployment

<table>
<tr>
<th align="left">Resource</th>
<th align="left">Configuration</th>
</tr>

<tr>
<td>Operating System</td>
<td>Ubuntu Server 22.04</td>
</tr>

<tr>
<td>Memory</td>
<td>8 GB RAM</td>
</tr>

<tr>
<td>CPU</td>
<td>2 vCPUs</td>
</tr>

<tr>
<td>Storage</td>
<td>100 GB</td>
</tr>

<tr>
<td>Network</td>
<td>Private VLAN</td>
</tr>

</table>

---

## Capabilities

- centralized log collection
- security alerting
- host-based intrusion detection
- system integrity monitoring
- endpoint telemetry

Agents installed on Windows systems send security data to the Wazuh server for analysis. :contentReference[oaicite:2]{index=2}

---

## Setup Documentation

➡ **[Wazuh Installation Guide](wazuh-install.md)**

This guide includes:

- Wazuh server deployment
- Windows agent installation
- dashboard configuration
- agent connectivity verification
