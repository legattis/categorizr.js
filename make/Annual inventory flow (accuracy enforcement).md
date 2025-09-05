flowchart TD
    S[Start Inventory Cycle] --> S1[Generate EIL Due List]
    S1 --> S2[Assign IMS & Schedule]
    S2 --> S3[Scan & Verify EE against system]
    S3 -->|Match| S4[Mark Verified]
    S3 -->|Not Found/Discrepancy| S5[Exception Record]

    S5 --> S6[Follow-up Actions]\n(Search, CO inquiry, MH trace)
    S6 --> S7{Resolved?}
    S7 -->|Yes| S4
    S7 -->|No| S8[Initiate ROS (PPM-ROS-YYYY-####)]

    S4 --> S9[Compute EIL Accuracy %]
    S9 -->|>=95%| S10[Close Inventory for EIL]
    S9 -->|<95%| S11[Schedule Re-check ≤ 6 months]

    S10 --> E[End]
    S11 --> E
