sequenceDiagram
    autonumber
    participant CO as CO/Delegate
    participant IN as Intake (Change Request)
    participant IMS as IMS (Authoritative updates)
    participant MH as Material Handling
    participant PAD as PADMD Record
    participant LOG as Movement Log

    CO->>IN: Submit location change (PPM-LOC-YYYY-####)\nEE#, from/to location, justification
    IN->>IMS: Route with EIL metadata
    par Physical vs Data
        IMS->>PAD: Update official location (Deployment stage)
        MH->>LOG: Record physical move (date/time/by whom)
    end
    IMS->>CO: Confirmation (updated)
