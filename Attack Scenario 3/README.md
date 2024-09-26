# Attack 3 Summary: SQL Injection Attack

## Stages of the Attack

### Origins

The attacker initiates the attack by targeting the SQL databases of the Solaris Health 360 application. The goal is to exploit vulnerable input fields to inject malicious SQL queries, enabling the attacker to steal, modify, or delete sensitive health records.

### Reconnaissance

The attacker analyzes the application architecture to identify where the SQL database is accessed. They focus on discovering input fields or API endpoints that are not properly sanitized and could be vulnerable to SQL injection.

### Weaponization

Once a vulnerable input field or endpoint is identified, the attacker crafts a malicious SQL payload designed to manipulate or bypass the existing SQL queries. This payload allows the attacker to execute unauthorized SQL commands and interact directly with the database, or execute code directly.

### Delivery

The attacker delivers the malicious SQL payload through a vulnerable input field or API endpoint, exploiting the lack of proper input validation.

### Exploitation

The attacker exploits the lack of proper input sanitization to execute malicious SQL queries. This allows them to retrieve sensitive information, alter database records, or escape the SQL statement to execute arbitrary commands.

### Installation

Once access is gained, the attacker can use code execution to install a backdoor, ensuring persistent access to the database and application for future exploitation.

### Actions on Objectives

With control over the database, the attacker can extract sensitive patient data, alter records to disrupt operations, or manipulate information, potentially causing harm to patients and the healthcare system.

```mermaid
flowchart LR
    A[Reconnaissance] -->|Identify vulnerable input fields and endpoints| B
    B[Weaponization] -->|Craft malicious SQL payload to exploit vulnerabilities| C
    C[Delivery] -->|Deliver payload through vulnerable input fields or API endpoints| D
    D[Exploitation] -->|Exploit lack of input sanitization to execute malicious SQL queries| E
    E[Installation] -->|Install backdoor via code execution for persistent access| F
    F[Command and Control] -->|Establish communication with C&C server for ongoing control| G
    G[Actions on Objectives] -->|Extract or modify sensitive data, disrupt operations| G
