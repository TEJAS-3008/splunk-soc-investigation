# SOC Investigation Workflow

```mermaid
flowchart TD
    A[Security Telemetry / Dataset] --> B[Data Onboarding]
    B --> C[Data Validation]
    C --> D[Source Type / Parsing]
    D --> E[Field Extraction / Normalization]
    E --> F[Detection & Hunting]
    F --> G[Investigation]
    G --> H[Correlation & Pivoting]
    H --> I[Evidence / Timeline]
    I --> J[Analyst Assessment]
    J --> K[Detection / Recommendations]
    K --> L[Documentation]
