flowchart LR
    O[Outage Trigger] --> ET[Email Templates Enforced]
    ET -->|Subject uses Unique ID| ID[[PPM-TYPE-YYYY-####]]
    ET --> EB[Body fields: EIL, CO, IMS, desc]
    ID --> U[Uber-Tracker Row Created]
    EB --> U

    U --> R{System Restored?}
    R -->|No| U
    R -->|Yes| MIG[Reconcile into PADMD\n(use same Unique ID)]
    MIG --> CL[Mark tracker row Reconciled]


Subject line rule (examples to paste into your SOP):
    [PPM-ERQ-2025-0147] – New Monitor for OR
[PPM-TRN-2025-0083] – Turn-in: Lab Equipment
[PPM-ROS-2025-0021] – Missing Ultrasound Machine
[PPM-LOC-2025-0312] – Location Change: EE#123456

