classDiagram
    class Asset {
      +EE#: string
      +EIL: string
      +ServiceLine: string
      +Status: enum
    }
    class EIL {
      +EIL: string
      +CO: person
      +CO_Alternates: list
    }
    class Request {
      +ID: string  "PPM-ERQ-YYYY-####"
      +Type: enum  "ERQ|TRN|ROS|LOC..."
      +EIL: string
      +Owner_IMS: person
      +Status: enum
    }
    class MovementEvent {
      +ID: string
      +EE#: string
      +From: location
      +To: location
      +When: datetime
      +By: person "MH"
    }
    class InventoryResult {
      +EIL: string
      +Date: date
      +AccuracyPct: float
      +Exceptions: list
    }
    class ROSCase {
      +ID: string  "PPM-ROS-YYYY-####"
      +Stage: enum "Initiated|Review|Closed"
      +CloseBy: date  "<=60 days"
    }
    class DispositionCase {
      +ID: string  "PPM-TRN-YYYY-####"
      +Route: enum "Excess|Unicor|Recycle|Disposal"
      +FinalConf: doc
    }
    class BillOfHealth {
      +Asset: EE#
      +Shop: enum "OIT|Biomed|FMS"
      +Findings: text
      +Date: date
    }

    EIL "1" -- "many" Asset : owns >
    EIL "1" -- "many" InventoryResult : measured_by >
    Asset "1" -- "many" MovementEvent : moved_via >
    Request "1" -- "1" Asset : about >
    Request "1" -- "1" EIL : scoped_to >
    ROSCase "1" -- "1" Asset : investigates >
    DispositionCase "1" -- "1" Asset : retires >
    DispositionCase "1" -- "0..1" BillOfHealth : requires >
