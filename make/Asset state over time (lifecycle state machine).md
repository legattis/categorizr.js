stateDiagram-v2
    [*] --> Planned
    Planned --> Acquired : Tagged @ Receipt\n(EIL linked)
    Acquired --> Deployed : IMS sets location
    Deployed --> Maintained : Annual inventory/repairs/loans
    Maintained --> Reused : BoH OK + Transfer/Reuse
    Maintained --> Survey : Missing/Unresolved --> ROS
    Survey --> Disposed : Closed (<=60 days)
    Reused --> Maintained
    Maintained --> Disposed : Turn-in -> Route -> Confirm
    Disposed --> [*]
