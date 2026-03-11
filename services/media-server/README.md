<h1 align="center">Media Server Stack</h1>

<p align="center">
Automated media server built using Docker containers to manage, download, and stream media within the homelab network.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Media_Server-Jellyfin-00a4dc?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Automation-Sonarr/Radarr-purple?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Indexer-Jackett-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Containers-Docker-2496ed?style=for-the-badge"/>
</p>

---

## ⚠ Legal Notice

This lab environment is intended for **educational and personal media management purposes only**.

Only download, stream, or store media that you **legally own or have permission to access**.

Examples include:

- public-domain films
- personal media collections
- legally purchased digital media

Do **not** use this system to distribute or download copyrighted material without authorization.

---

## Overview

This stack provides a fully automated pipeline for managing media.

The system includes services responsible for:

- indexing media sources
- downloading media
- organizing files
- streaming content to clients

---

## Media Stack Components

<table>
<tr>
<th align="left">Service</th>
<th align="left">Purpose</th>
</tr>

<tr>
<td>Jellyfin</td>
<td>Media streaming server</td>
</tr>

<tr>
<td>Sonarr</td>
<td>TV show automation and management</td>
</tr>

<tr>
<td>Radarr</td>
<td>Movie automation and management</td>
</tr>

<tr>
<td>Jackett</td>
<td>Indexer aggregator</td>
</tr>

<tr>
<td>qBittorrent</td>
<td>Download client</td>
</tr>

<tr>
<td>Gluetun</td>
<td>VPN gateway container</td>
</tr>

<tr>
<td>FlareSolverr</td>
<td>Cloudflare protection bypass helper</td>
</tr>

</table>

---

## Deployment Model

All services are deployed using **Docker Compose**.

This allows the entire media stack to be managed with a single configuration file and started with one command.

---

## Pipeline Workflow

Indexer (Jackett)<br>
│<br>
V<br>
Automation (Sonarr / Radarr)<br>
│<br>
V<br>
Download Client (qBittorrent)<br>
│<br>
V<br>
Media Organization<br>
│<br>
V<br>
Jellyfin Streaming Server<br>

---

## Setup Documentation

➡ **[Jellyfin Media Stack Setup](MediaServerAutomationDocs)**

The guide includes:

- Docker installation
- firewall configuration
- media folder structure
- Docker Compose configuration
- service configuration
- automated media pipeline setup
