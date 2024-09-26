```mermaid
  sequenceDiagram
    participant Attacker
    participant SolariHealthApp
    participant CnCServer
    participant BackendServer
    participant DataLake
    activate Attacker
    Attacker->>SolariHealthApp: Identify vulnerabilities in machine processes and data lake
    SolariHealthApp->>Attacker: Vulnerabilities identified
    deactivate Attacker
    activate Attacker
    Attacker->>SolariHealthApp: Craft exploit targeting machine processes
    SolariHealthApp->>Attacker: Exploit crafted
    deactivate Attacker
    activate Attacker
    Attacker->>SolariHealthApp: Inject malicious payload through vulnerable API
    SolariHealthApp->>BackendServer: Payload delivered to machine processes
    activate BackendServer
    BackendServer->>DataLake: Malicious payload executed, data access gained
    deactivate BackendServer
    activate Attacker
    BackendServer->>CnCServer: Communication established
    CnCServer->>BackendServer: Commands issued
    BackendServer->>CnCServer: Actions performed (Data exfiltration, workflow disruption)
    deactivate Attacker
