sequenceDiagram
    autonumber
    participant CO as Custodial Officer / Requestor
    participant IN as Intake (Form)
    participant IMS as IMS
    participant PAD as PADMD Record
    participant DB as Compliance Views / Dashboards

    CO->>IN: Submit request (PPM-ERQ-YYYY-####)\nEIL, service line, description
    IN->>IMS: Route to assigned IMS (with metadata)
    IMS->>PAD: Create/Update canonical PADMD record
    IMS->>DB: Expose status (Active/Owner/Due Date)
    CO-->>DB: View status (no file chasing)
    IMS->>CO: Resolution/closure notice
    IMS->>PAD: Finalize record + close request
