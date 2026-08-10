# Investigation Workflow

## Linux Base64 Decoding — T1140

```mermaid
flowchart TD
    A[Linux Auditd Dataset] --> B[Upload to Splunk]
    B --> C[Validate Ingestion]
    C --> D[Identify EXECVE Events]
    D --> E[Identify base64 Executions]
    E --> F[Identify -d / --decode]
    F --> G[Inspect Supplied Input]
    G --> H[Analyze Event Timeline]
    H --> I[Assess Maliciousness]
    I --> J[Develop SPL Detection]
    J --> K[Document Findings]
