<!-- TITLE & HEADLINES -->
<div align="center">
  <br />
  <a href="https://github.com/yourusername/datasentry">
    <img src="https://img.shields.io/badge/🛡️%20Security-Level%20Critical-red?style=for-the-badge" alt="Logo">
  </a>
  
  <h1 align="center">DataSentry</h1>

  <h3 align="center">
    The AI-Powered Privacy & Security Orchestrator
  </h3>

  <p align="center">
    <b>An autonomous multi-agent system that detects, analyzes, and remediates<br>
    data leaks in code, notebooks, and documents before they happen.</b>
  </p>

  <!-- BADGES -->
  <p align="center">
    <a href="https://www.python.org/">
      <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white" alt="python">
    </a>
    <a href="https://deepmind.google/technologies/gemini/">
      <img src="https://img.shields.io/badge/AI-Google%20Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white" alt="gemini">
    </a>
    <a href="#">
      <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="license">
    </a>
    <a href="#">
      <img src="https://img.shields.io/badge/Status-Production%20Ready-green?style=for-the-badge" alt="status">
    </a>
  </p>
  <br />
</div>

<hr />

<!-- TABLE OF CONTENTS -->
<details>
  <summary><b>📋 Table of Contents</b> (Click to expand)</summary>
  <br />
  
  - [The Problem](#-the-problem)
  - [The Solution](#-the-solution)
  - [Architecture](#-architecture)
  - [Key Features](#-key-features)
  - [Installation](#-installation)
  - [Usage](#-usage)
  - [Sample Reports](#-sample-reports)
  - [Contributing](#-contributing)
  
  <br />
</details>

<!-- MAIN CONTENT -->

## 🚨 The Problem

Data leaks cost organizations millions annually. Data scientists and developers often accidentally leave:
*   ❌ **API Keys** (AWS, OpenAI, Stripe) hardcoded in notebooks.
*   ❌ **Customer PII** (Emails, SSNs, Phone Numbers) in printed output cells.
*   ❌ **Internal Credentials** in configuration files.

## ✨ The Solution

**DataSentry** (formerly Privacy Guardian) is not just a regex scanner. It is an **Agentic AI System** that understands context.

<blockquote>
  "DataSentry acts as a specialized security engineer in the loop, catching vulnerabilities that standard tools miss."
</blockquote>

---

## 🏗️ Architecture

DataSentry operates using a **Multi-Agent Orchestration** pattern:

<div align="center">
  <pre>
User Input ➔ 🤖 [Orchestrator Agent]
                 ⬇️
          [📂 Ingestion Engine]
          (Parses .ipynb, .pdf, .csv)
                 ⬇️
    [👤 PII Scanner] + [🔑 Secret Scanner]
       (Parallel AI Detection)
                 ⬇️
        [⚖️ Risk Evaluator Agent]
                 ⬇️
        [🛠️ Remediation Engine]
                 ⬇️
      📊 Final Dashboard & JSON Report
  </pre>
</div>

---

## ⚡ Key Features

<table>
  <tr>
    <th width="30%">Feature</th>
    <th width="70%">Description</th>
  </tr>
  <tr>
    <td><b>🔍 Context-Aware Scanning</b></td>
    <td>Distinguishes between dummy variables (<code>key="123"</code>) and real secrets using Gemini AI.</td>
  </tr>
  <tr>
    <td><b>🛡️ Multi-Agent System</b></td>
    <td>5 specialized agents working in parallel to detect PII, Secrets, and Logic flaws.</td>
  </tr>
  <tr>
    <td><b>📊 Risk Scoring</b></td>
    <td>Generates a weighted risk score (0-100) and assigns severity (Low to Critical).</td>
  </tr>
  <tr>
    <td><b>🔧 Auto-Remediation</b></td>
    <td>Generates actual code patches (e.g., "Rotate this key and use <code>os.getenv</code>").</td>
  </tr>
  <tr>
    <td><b>🔄 Auto-Retry Logic</b></td>
    <td>Built-in resilience for API rate limits and quotas.</td>
  </tr>
</table>

---
