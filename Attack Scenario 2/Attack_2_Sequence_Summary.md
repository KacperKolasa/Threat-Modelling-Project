# Summary MITRE ATT&CK Sequence

# Attack Description

The attacker is an APT who has identified weaknesses in the automation workflows and data lake of Solaris Health 360. By targeting vulnerabilities in the machine processes, the attacker gains direct access to the data lake without needing to bypass traditional security measures like firewalls or access controls. Instead, the attacker exploits flaws in the automation processes to manipulate data flows and extract sensitive health information, leveraging access to critical data pipelines for disruption and exfiltration.

# Methodology

The attack sequence below utilises the MITRE ATT&CK framework along with the commonly used techniques.

```mermaid

flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    
    Reconnaissance[Reconnaissance] -->|Attacker analyzes machine processes and data lake for vulnerabilities in data pipelines| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Craft malicious payloads targeting automation workflows and data storage| Delivery[Delivery]
    Delivery[Delivery] -->|Inject payloads via compromised admin accounts or vulnerable APIs| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Exploit vulnerabilities such as SQL injection or API exploitation| Installation[Installation]
    Installation[Installation] -->|Install backdoors to maintain control over machine processes and data lake| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Establish communication with C&C server| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Exfiltrate sensitive health data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Disrupt automated workflows and corrupt data| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Delivery -->|T1071.001 - Application Layer Protocol: Web Protocols| MITRE
    Exploitation -->|T1190 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1071.001 - Command and Scripting Interpreter| MITRE
    Installation -->|T1106 - Execution through API| MITRE
    Command_Control -->|T1102 - Web Service| MITRE
    Command_Control -->|T1105 - Ingress Tool Transfer| MITRE
    Actions_Objectives -->|T1530 - Data from Cloud Storage Object| MITRE
    Actions_Objectives -->|T1565.001 - Data Manipulation| MITRE
    end
