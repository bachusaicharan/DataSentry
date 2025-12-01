🛡️ DataSentry
AI-Powered Privacy & Security Orchestrator
![alt text](https://img.shields.io/badge/python-3.10+-blue.svg)

![alt text](https://img.shields.io/badge/AI-Google%20Gemini-8E75B2)

![alt text](https://img.shields.io/badge/License-MIT-yellow.svg)

![alt text](https://img.shields.io/badge/Status-Production%20Ready-green)
DataSentry (formerly Project Privacy Guardian) is an automated, multi-agent security system designed to detect, analyze, and remediate data leaks in code and documents.
Powered by Google Gemini, DataSentry acts as a specialized security team in a box—scanning Jupyter notebooks, PDFs, and code files for PII (Personally Identifiable Information) and exposed API secrets before they are committed or shared.
🚨 The Problem
Data leaks cost organizations millions annually. Data scientists and developers often accidentally leave:
API Keys (AWS, OpenAI, Stripe) hardcoded in notebooks.
Customer PII (Emails, SSNs, Phone Numbers) in printed output cells.
Internal Credentials in configuration files.
✨ The Solution: DataSentry
DataSentry is not just a regex scanner. It is an Agentic AI System that understands context.
🔍 Context-Aware Scanning: Distinguishes between a dummy variable key="123" and a real sk-proj-... API key.
🛡️ Multi-Agent Architecture: Orchestrates 5 specialized sub-agents for Ingestion, PII Detection, Secret Scanning, Risk Assessment, and Remediation.
📊 Automated Reporting: Generates risk scores (0-100), visual dashboards, and detailed audit logs.
🔧 Actionable Remediation: Doesn't just find the bug—it writes the code to fix it (e.g., "Rotate this key and use os.getenv").
🏗️ Architecture
DataSentry operates using a coordinator-worker agent pattern:
code
Mermaid
graph TD
    A[User Input] --> B[Orchestrator Agent]
    B --> C[Ingestion Engine]
    B --> D[PII Scanner]
    B --> E[Secret Detector]
    D & E --> F[Risk Evaluator]
    F --> G[Remediation Planner]
    G --> H[Final Report & Dashboard]
Agent/Component	Function
Ingestion Agent	Parses .ipynb, .pdf, .csv, .json, .txt to extract raw content.
PII Scanner	Hybrid (LLM + Pattern Matching) detection of emails, phones, SSNs, and addresses.
Secret Scanner	Identifies 50+ types of credentials (AWS, GCP, Azure, OpenAI, GitHub).
Risk Evaluator	Calculates a weighted risk score (0-100) based on finding severity and context.
Remediation	Generates specific code patches and masking strategies.
🚀 Getting Started
Prerequisites
Python 3.10+
A Google Cloud API Key (for Gemini)
Installation
Clone the repository
code
Bash
git clone https://github.com/yourusername/datasentry.git
cd datasentry
Install dependencies
code
Bash
pip install -r requirements.txt
Configure API Key
Set your Google API key as an environment variable:
code
Bash
export GOOGLE_API_KEY="your_api_key_here"
(Or configure it via secrets.toml if using Streamlit/Kaggle).
💻 Usage
1. The One-Command Scan
DataSentry is designed for automation. You can scan a file with a single line of Python:
code
Python
from datasentry import DataSentryAgent

# Initialize the agent
agent = DataSentryAgent()

# Scan a notebook (or PDF, CSV, etc.)
results = agent.scan_file("my_project_notebook.ipynb")

# View the summary
print(f"Risk Score: {results['summary']['risk_score']}/100")
2. Batch Processing
Scan an entire directory of files to generate a compliance report:
code
Python
files_to_scan = ["data_pipeline.py", "analysis.ipynb", "report.pdf"]
agent.batch_scan(files_to_scan)
3. Interactive Mode
You can chat with the agent to ask specific security questions:
code
Python
response = agent.run("How do I best secure the AWS keys found in data_pipeline.py?")
print(response)
📊 Sample Output
When DataSentry detects vulnerabilities, it provides a detailed breakdown:
code
JSON
{
  "risk_score": 85,
  "severity": "CRITICAL",
  "findings": {
    "secrets": [
      {
        "type": "OpenAI API Key",
        "location": "Cell 2, Line 4",
        "suggestion": "Move to environment variable"
      }
    ],
    "pii": [
      {
        "type": "SSN",
        "count": 5,
        "context": "Customer dataframe print output"
      }
    ]
  }
}
🛠️ Configuration
You can customize the strictness and model in config.py:
code
Python
CONFIG = {
    "team": "Singleton Labs",
    "model": "gemini-2.0-flash-001", # Supports 1.5-flash and Pro
    "strict_mode": True,
    "pii_threshold": "high"
}
🤝 Contributing
Contributions are welcome! Please check the CONTRIBUTING.md for guidelines.
Fork the Project
Create your Feature Branch (git checkout -b feature/AmazingFeature)
Commit your Changes (git commit -m 'Add some AmazingFeature')
Push to the Branch (git push origin feature/AmazingFeature)
Open a Pull Request
📄 License
Distributed under the MIT License. See LICENSE for more information.
<div align="center">
<p>Built with ❤️ by <strong>Singleton Labs</strong></p>
<p><em>Protecting data, one scan at a time.</em></p>
</div>
