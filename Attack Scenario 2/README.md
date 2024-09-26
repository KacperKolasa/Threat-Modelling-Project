# Attack 2 Summary: Attack against Machine Processes and the data lake

## Stages of the Attack

### Origins

The attacker targets the Solaris Health 360 application’s machine processes and data lake, aiming to disrupt automated operations and access the large amount of sensitive health data stored in it.

### Reconnaissance

The attacker conducts research to understand the architecture of the machine processes and data lake, identifying weak points in data pipelines, automation workflows, and access controls. This includes analyzing how data flows between systems and where potential vulnerabilities in processing and storage may exist.

### Weaponization

The attacker crafts malicious scripts and payloads designed to exploit the vulnerabilities found in the machine processes and data lake. These payloads are aimed at disrupting automated workflows, corrupting data, and exfiltrating sensitive health information from the data lake.

### Delivery

The attacker deploys the malicious payload by infiltrating the system through compromised admin accounts or vulnerable interfaces in the automation processes, injecting the malware into the machine workflows and data pipelines.

### Exploitation

The attacker exploits vulnerabilities in the machine processes and data lake using methods such as SQL injection to manipulate queries, command injection to execute arbitrary code within automated workflows, or API exploitation to gain unauthorized access to sensitive data. These exploits allow the attacker to disrupt data processing, exfiltrate sensitive health information, and manipulate the integrity of stored data.

### Installation

Once access is gained, the attacker installs backdoors in the machine processes to maintain persistent control over automated workflows and the data lake. This may include planting malware that allows ongoing manipulation of data pipelines and continued access to sensitive health information.

### Actions on Objectives

With control over the machine processes and data lake, the attacker exfiltrates sensitive health data, including patient records and research information. Additionally, the attacker may alter data in the workflows, leading to inaccurate medical reports or disrupt automated processes, causing system outages or operational delays in critical healthcare services.
```mermaid
flowchart LR
    A[Reconnaissance] -->|Identify vulnerabilities in machine processes and data lake| B
    B[Weaponization] -->|Craft malicious payload targeting automation workflows and data| C
    C[Delivery] -->|Inject malware via compromised admin accounts or vulnerable interfaces| D
    D[Exploitation] -->|Execute exploits such as SQL Injection, Command Injection, or API exploitation| E
    E[Installation] -->|Install backdoors to maintain control over machine processes and data lake| F
    F[Command and Control] -->|Establish communication with C&C server to issue commands| G
    G[Actions on Objectives] -->|Exfiltrate sensitive data, disrupt workflows, and manipulate data| G
