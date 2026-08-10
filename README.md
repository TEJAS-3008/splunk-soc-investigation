# SOC Investigation & Detection Lab

A hands-on Security Operations Center (SOC) laboratory focused on security
monitoring, SIEM-based investigation, threat detection, and incident analysis.

The project currently focuses on **Splunk**, with **Elastic Stack** investigations
planned as the project expands.

---

## 🎯 Objectives

This project is designed to build practical SOC analyst skills through
investigating security telemetry and developing detection logic.

Key objectives:

- Ingest and validate security telemetry
- Understand SIEM data sources and sourcetypes
- Perform field extraction and normalization
- Develop SPL-based threat hunting queries
- Investigate suspicious activity
- Build investigation timelines
- Map activity to MITRE ATT&CK
- Develop reusable detection logic
- Document findings and evidence
- Reproduce investigations across multiple SIEM platforms

---

## 🔄 SOC Investigation Workflow

The project follows this general workflow:

```mermaid
flowchart TD
    A[Security Telemetry / Dataset] --> B[Data Onboarding]
    B --> C[Data Validation]
    C --> D[Parsing & Field Extraction]
    D --> E[Normalization]
    E --> F[Detection & Threat Hunting]
    F --> G[Investigation]
    G --> H[Correlation & Pivoting]
    H --> I[Evidence & Timeline]
    I --> J[Analyst Assessment]
    J --> K[Detection / Recommendations]
    K --> L[Documentation]

