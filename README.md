# GUARDIAN-X
## Multimodal Multi-Agent Guardrails & Zero-Trust Action Firewall

[![Python](https://img.shields.io/badge/Python-3.11%2B-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/API-FastAPI-009688.svg)](https://fastapi.tiangolo.com/)
[![Streamlit](https://img.shields.io/badge/UI-Streamlit-FF4B4B.svg)](https://streamlit.io/)
[![Pytest](https://img.shields.io/badge/Testing-Pytest-0A9EDC.svg)](https://pytest.org/)
[![Security](https://img.shields.io/badge/Security-Zero--Trust-critical.svg)]
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **GUARDIAN-X** is a multimodal AI security architecture designed to protect
> agentic AI systems from prompt injection, malicious instructions, destructive
> tool requests, path traversal, credential exposure, and unsafe autonomous
> actions.

GUARDIAN-X introduces a strict **Zero-Trust Action Firewall** between AI
agents and executable tools.

No agent is allowed to directly execute a tool.

Every proposed action must pass through the security perimeter before execution.

---

# Table of Contents

- [Overview](#overview)
- [Problem](#problem)
- [Solution](#solution)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Multi-Agent System](#multi-agent-system)
- [Security Pipeline](#security-pipeline)
- [Risk & Policy Engine](#risk--policy-engine)
- [Action Firewall](#action-firewall)
- [Multimodal Security](#multimodal-security)
- [Attack Memory](#attack-memory)
- [Security Logging](#security-logging)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Testing](#testing)
- [Evaluation](#evaluation)
- [Example Scenarios](#example-scenarios)
- [Security Principles](#security-principles)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)
- [License](#license)

---

# Overview

Modern AI agents are increasingly capable of interacting with tools such as:

- File systems
- Databases
- Calculators
- APIs
- Code execution environments
- External services

This capability introduces a major security problem.

An AI agent that can freely execute tools may potentially be manipulated into:

- Revealing confidential information
- Executing destructive operations
- Reading protected files
- Following prompt injections
- Bypassing security policies
- Accessing unauthorized resources

GUARDIAN-X addresses this problem by placing a dedicated security perimeter
between the AI reasoning layer and the execution layer.

The architecture follows a simple principle:

```text
UNTRUSTED INPUT
      ↓
SECURITY ANALYSIS
      ↓
RISK ASSESSMENT
      ↓
POLICY DECISION
      ↓
ACTION FIREWALL
      ↓
AUTHORIZED TOOL
      ↓
AUDIT LOG
