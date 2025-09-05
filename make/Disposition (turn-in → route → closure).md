flowchart TD
    TI[Turn-in Request (PPM-TRN-YYYY-####)] --> CMR[CMR/Source Proof Attached]
    CMR --> INSP[Inspections: OIT/Biomed/FMS]
    INSP -->|Reusable| BOH[BoH required (shop submits)]
    INSP -->|Not reusable| RTE2[Recycle/Disposal]
    BOH --> RTE1[Excess/Reuse Channel]
    RTE1 --> CONF[Final Confirmation & Update]
    RTE2 --> CONF

    subgraph Custody Chain
      RC[MH Receives/Staging]
      MV[MH Physical Transfer]
    end
    TI --> RC --> MV
    MV --> CONF

    CONF --> CL[Close Disposition Case]\n(attach confirmations)
