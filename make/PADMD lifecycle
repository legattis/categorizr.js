flowchart LR
    %% Top-level lifecycle
    P[Planning] --> A[Acquisition] --> D[Deployment] --> M[Maintenance] --> X[Disposition]

    %% Data/control artifacts at each stage
    subgraph SG_P[Planning - Data/Controls]
      P1[SEPG record (need/justification)]
      P2[EIL assignment (CO of record)]
      P3[Equipment Committee notes]
      P4[5-year replacement forecast]
      P --> P1 --> P2 --> P3 --> P4
    end

    subgraph SG_A[Acquisition - Data/Controls]
      A1[Requisition/Approval]
      A2[Receiving Event (MH)]
      A3[EE Tagging @ Receipt]
      A4[Link to EIL at tagging]
      A --> A1 --> A2 --> A3 --> A4
    end

    subgraph SG_D[Deployment - Data/Controls]
      D1[Placement record]
      D2[CO Change Request via Intake]
      D3[IMS updates official location]
      D4[Movement log (MH)]
      D --> D1 --> D2 --> D3 --> D4
    end

    subgraph SG_M[Maintenance - Data/Controls]
      M1[Annual Inventory result]
      M2[Exceptions & Follow-ups]
      M3[Loan Registry entries]
      M4[Bill-of-Health (BoH) for reuse]
      M --> M1 --> M2 --> M3 --> M4
    end

    subgraph SG_X[Disposition - Data/Controls]
      X1[Turn-in case]
      X2[Inspections: OIT/Biomed/FMS]
      X3[ROS as required]
      X4[Excess/Unicor/Recycle route]
      X5[Final disposal confirmation]
      X --> X1 --> X2 --> X3 --> X4 --> X5
    end
