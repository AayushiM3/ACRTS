# ACRTS - Adaptive Cyber Resilience and Automated Threat Neutralization System
ACRTS is a Python-based cybersecurity incident response platform designed to automate log analysis, attack detection, risk assessment, MITRE ATT&CK mapping, and incident reporting. The system processes logs from multiple sources, identifies suspicious activity using detection rules, assigns contextual risk scores, and presents findings through an interactive dashboard.

## Team
Name and Primary Responsibility
- Jahnavi Singh: Detection Logic & System Architecture
- Darsh Bindra:	Backend Development & Log Parsing
- Aayushi Malik:	Database, Risk Scoring & Reporting
- Mohini:	Dashboard & Frontend Development

## Contributions
As the primary contributor for the database, risk analysis, and reporting modules, I:

- Designed and implemented the SQLite-based persistence layer for storing and retrieving security incidents.
- Developed a context-aware risk scoring engine that evaluates incidents using attack type, time-based weighting, and repeated source activity.
- Built automated PDF report generation for incident summaries and security reporting workflows.
- Contributed to system integration, testing, and validation across detection, backend, and dashboard modules.

## Key Features
- Multi-source log parsing (Windows, Linux, and Apache logs)
- Rule-based attack detection and classification
- MITRE ATT&CK technique mapping
- Context-aware risk scoring
- SQLite-backed incident storage
- Interactive Streamlit dashboard
- Automated PDF report generation
- Simulated incident response actions

## MITRE ATT&CK Mapping
MITRE is that huge list of attacker tactics and techniques. We mapped the detections to IDs so we remember which tactic matches what.

| Attack | MITRE ID | Tactic |
| Brute Force | T1110 | Credential Access |
| RDP Tunneling | T1021.001 | Lateral Movement |
| SQL Injection | T1190 | Initial Access |
| Port Scanning | T1046 | Discovery |
| Privilege Escalation | T1068 | Privilege Escalation |
| C2C Activity | T1071 | Command and Control |



## Tech Stack
Python, SQLite, Streamlit, Pandas, Altair, FPDF2, Regex

## Project Structure
```
main.py               # CLI engine
log_parser.py         # parses different log formats
sample_logs/          # fake logs for demo
config.py             # settings and thresholds
mitre_mapper.py       # MITRE mapping
risk_scorer.py        # risk scoring rules
detector.py           # detection logic
responder.py          # demo response actions
database.py           # SQLite helper
report_generator.py   # PDF report
dashboard.py          # Streamlit UI
requirements.txt      # deps
README.md             # this doc
```

## Installation and Running
1. Clone or download this repo on your Mac.
2. Create a venv if you like; we usually just `python -m venv .venv && source .venv/bin/activate`.
3. `pip install -r requirements.txt`.
4. `python main.py` to run detections. We mostly use option 4 to scan all sample logs.
5. `streamlit run dashboard.py` to open the dashboard. Keep the terminal open because Streamlit needs it.
6. If you want a PDF, use the download button in the dashboard after you have incidents.

## Future Ideas
- Add GeoIP and ASN context for the IPs.
- Hook in a real mail sender when not in demo mode.
- Add more web attack patterns and maybe DNS logs.

## Acknowledgements
Developed as part of a university minor project in cybersecurity with a focus on incident response, threat detection, and security automation.

Raise an issue for any problems. Also feel free to use this or suggest improvements.
