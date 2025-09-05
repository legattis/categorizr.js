flowchart LR
    I[Initiate ROS (PPM-ROS-YYYY-####)] --> A[Assemble Case File]
    A --> Q[AO/Board Review & Investigation]
    Q --> D{Determination}
    D -->|Negligence found| R1[Assess Liability/Recovery]
    D -->|No negligence| R2[Document Findings]
    R1 --> C[Close ROS ≤ 60 days]
    R2 --> C

    %% Visibility/controls
    subgraph Visibility & Controls
      V1[Per-IMS ROS View (status/stage)]
      V2[Auto reminders: 30/45/60 day]
      V3[Leadership summary widget]
    end
    I -.-> V1
    Q -.-> V2
    C -.-> V3
