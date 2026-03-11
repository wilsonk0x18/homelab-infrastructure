<h1 align="center">Local AI Server</h1>

<p align="center">
Self-hosted AI inference server running <b>Ollama</b> with <b>Open WebUI</b> to provide a browser-based interface for running local large language models on GPU hardware.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AI-Ollama-black?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/UI-Open_WebUI-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/GPU-RTX_2080_Super-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Models-Qwen_8B-purple?style=for-the-badge"/>
</p>

---

## Overview

This service provides a **local AI environment for running large language models directly on homelab hardware**.

The system uses **Ollama** as the inference engine and **Open WebUI** to provide an accessible web interface.  
Models run locally on an **NVIDIA RTX 2080 Super**, allowing private and offline AI interaction without relying on cloud services.

The server is accessible:

- locally over the LAN
- remotely through **Tailscale**

To conserve power, the system automatically **enters suspend mode after 15 minutes of inactivity** and can be restarted remotely using **Wake-on-LAN**.

---

## Service Architecture

<table>
<tr>
<th align="left">Component</th>
<th align="left">Purpose</th>
</tr>

<tr>
<td>Ollama</td>
<td>Runs and manages local language models</td>
</tr>

<tr>
<td>Open WebUI</td>
<td>Browser-based interface for interacting with models</td>
</tr>

<tr>
<td>Docker</td>
<td>Container platform used to run the WebUI service</td>
</tr>

<tr>
<td>NVIDIA Drivers</td>
<td>GPU acceleration for model inference</td>
</tr>

<tr>
<td>Tailscale</td>
<td>Secure remote access to the AI server</td>
</tr>

</table>

---

## Models Used

| Model | Size | Purpose |
|------|------|------|
| Qwen 2.5 | 8B parameters | General-purpose LLM for chat, coding, and experimentation |

The **8B parameter model class** provides a good balance between performance and resource usage on consumer GPUs.

---

## System Features

- local LLM inference
- GPU acceleration
- browser-based AI interface
- LAN and remote access
- power-efficient idle management
- automatic suspend after inactivity
- Wake-on-LAN remote startup

---

## Setup Documentation

Full installation and configuration steps are available here:

➡ **[Ollama + Open WebUI Setup Guide](OllamaInstallDocs)**

The guide includes:

- Ubuntu 24.04 server setup
- NVIDIA driver installation
- Ollama installation
- Open WebUI deployment
- Qwen 8B model setup
- Tailscale remote access
- automatic idle suspend script
- Wake-on-LAN configuration
