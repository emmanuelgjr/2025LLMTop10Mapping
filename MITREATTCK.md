# OWASP Top 10 for LLM Applications 2025 Mapped to MITRE ATT&CK

The OWASP Top 10 for LLM Applications identifies the most critical vulnerabilities impacting AI models, while the [**MITRE ATT&CK**](https://attack.mitre.org/) framework provides a comprehensive collection of adversary tactics and techniques. Mapping these vulnerabilities to MITRE ATT&CK to bridge the gap between vulnerability identification and actionable mitigation, enabling a proactive approach to AI security for developers, security teams, and stakeholders.

| Vulnerability                   | MITRE ATT&CK Mapping                                                                 | Mitigation                                                                                           |
|---------------------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| LLM01:2025 Prompt Injection     | [Direct Prompt Injection (AML.T0051.000) - Influence Operations](https://atlas.mitre.org/techniques/AML.T0051.000)  | Implement input validation, human oversight, and adversarial testing                                |
|                                 | [Indirect Prompt Injection (AML.T0051.001) - Influence Operations](https://atlas.mitre.org/techniques/AML.T0051.001) |                                                                                                      |
| LLM02:2025 Sensitive Information Disclosure | [Data from Cloud Storage Object (T1530) - Exfiltration](https://attack.mitre.org/techniques/T1530/)  | Data sanitization, access controls, and federated learning                                          |
|                                 | [Application Layer Protocol (T1071) - Command and Control](https://attack.mitre.org/techniques/T1071/) |                                                                                                      |
| LLM03:2025 Supply Chain Risks   | [Supply Chain Compromise (T1195) - Initial Access](https://attack.mitre.org/techniques/T1195/)  | Component verification, patch management                                                            |
| LLM04:2025 Data and Model Poisoning | [Jailbreak Injection (AML.T0054) - Manipulation of Model Behaviors](https://atlas.mitre.org/techniques/AML.T0054) | Adversarial training, anomaly detection                                                             |
| LLM05:2025 Insecure Output Handling | [Command and Scripting Interpreter (T1059) - Execution](https://attack.mitre.org/techniques/T1059/) | Output filtering, rule enforcement                                                                  |
| LLM06:2025 Excessive Agency     | [System Script Proxy Execution (T1216) - Execution](https://attack.mitre.org/techniques/T1216/)  | Access control, privilege control                                                                   |
| LLM07:2025 System Prompt Leakage | [Indicator Removal on Host (T1070) - Defense Evasion](https://attack.mitre.org/techniques/T1070/)  | Prompt obfuscation, configuration reviews                                                           |
| LLM08:2025 Vector and Embedding Weaknesses | [Data Obfuscation (T1001) - Command and Control](https://attack.mitre.org/techniques/T1001/)  | Embedding validation, adversarial testing                                                           |
| LLM09:2025 Misinformation       | [Web Service (T1102) - Command and Control](https://attack.mitre.org/techniques/T1102/)  | Retrieval-augmented generation (RAG), human oversight                                               |
| LLM10:2025 Unbounded Consumption | [Endpoint Denial of Service (T1499) - Impact](https://attack.mitre.org/techniques/T1499/)  | Rate limiting, load balancing, monitoring                                                           |

---

### [LLM01:2025 Prompt Injection](https://genai.owasp.org/)
**Description:** Prompt Injection occurs when attackers manipulate the input prompts of LLMs to alter behaviour or outputs. These attacks can bypass safety measures, gain unauthorized access, or influence decisions.

#### MITRE ATT&CK Mapping
- **Direct Prompt Injection (AML.T0051.000)**
  - **Tactic:** Influence Operations
  - **Technique:** Injection of malicious input directly into LLM prompts to alter outputs. [Link](https://atlas.mitre.org/techniques/AML.T0051.000)
- **Indirect Prompt Injection (AML.T0051.001)**
  - **Tactic:** Influence Operations
  - **Technique:** Use of third-party sources or external content to indirectly influence LLM behaviour. [Link](https://atlas.mitre.org/techniques/AML.T0051.001)

#### Mitigations
- **Input Validation**: Implement robust input validation and filtering using libraries such as `pydantic`.
- **Human Oversight**: Use human-in-the-loop mechanisms for high-risk actions.
- **Adversarial Testing**: Regular adversarial testing to identify vulnerabilities.

---

### [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)
**Description:** LLMs risk disclosing sensitive data (e.g., PII, proprietary information) during interactions or through outputs, leading to privacy violations and data breaches.

#### MITRE ATT&CK Mapping
- **Data from Cloud Storage Object (T1530)**
  - **Tactic:** Exfiltration
  - **Technique:** Retrieval of sensitive data from cloud storage via compromised LLM prompts. [Link](https://attack.mitre.org/techniques/T1530/)
- **Application Layer Protocol (T1071)**
  - **Tactic:** Command and Control
  - **Technique:** Exploitation of protocol-based communication to extract sensitive information. [Link](https://attack.mitre.org/techniques/T1071/)

#### Mitigations
- **Data Sanitization**: Apply data sanitization and differential privacy techniques.
- **Access Controls**: Enforce strict access controls and clear user policies.
- **Federated Learning**: Implement federated learning to minimize centralized data collection.

---

### [LLM03:2025 Supply Chain Risks](https://genai.owasp.org/)
**Description:** Vulnerabilities arise from dependencies on third-party data, tools, or software integrated into LLM workflows.

#### MITRE ATT&CK Mapping
- **Supply Chain Compromise (T1195)**
  - **Tactic:** Initial Access
  - **Technique:** Compromising third-party tools, models, or datasets to influence LLM behaviour. [Link](https://attack.mitre.org/techniques/T1195/)

#### Mitigations
- **Component Verification**: Verify third-party components' integrity through code signing and cryptographic validation.
- **Patch Management**: Apply strong version control and patch management to secure dependencies.

---

### [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)
**Description:** Attackers can inject malicious data into training datasets, compromising model integrity or altering outputs.

#### MITRE ATT&CK Mapping
- **Jailbreak Injection (AML.T0054)**
  - **Tactic:** Manipulation of Model Behaviors
  - **Technique:** Bypassing LLM safety protocols to generate harmful responses. [Link](https://atlas.mitre.org/techniques/AML.T0054)

#### Mitigations
- **Adversarial Training**: Conduct adversarial training and robust validation of data sources.
- **Anomaly Detection**: Apply anomaly detection methods to identify unusual patterns in datasets.

---

### [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)
**Description:** Improper handling of LLM outputs can result in the leakage of sensitive information or execution of unsafe actions.

#### MITRE ATT&CK Mapping
- **Command and Scripting Interpreter (T1059)**
  - **Tactic:** Execution
  - **Technique:** Leveraging LLM-generated outputs to execute commands or scripts. [Link](https://attack.mitre.org/techniques/T1059/)

#### Mitigations
- **Output Filtering**: Implement output filtering and validation mechanisms.
- **Rule Enforcement**: Enforce strict rules for permissible output formats and contexts.

---

### [LLM06:2025 Excessive Agency](https://genai.owasp.org/)
**Description:** LLMs with excessive decision-making power can autonomously perform actions that impact business processes or user safety.

#### MITRE ATT&CK Mapping
- **System Script Proxy Execution (T1216)**
  - **Tactic:** Execution
  - **Technique:** Misuse of autonomous LLM functions to execute unauthorized actions. [Link](https://attack.mitre.org/techniques/T1216/)

#### Mitigations
- **Access Control**: Limit model access to critical functions.
- **Privilege Control**: Implement privilege control and role-based access for LLMs.

---

### [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)
**Description:** Exposure of system prompts can reveal internal configurations or enable targeted prompt injections.

#### MITRE ATT&CK Mapping
- **Indicator Removal on Host (T1070)**
  - **Tactic:** Defense Evasion
  - **Technique:** Alteration or deletion of system prompts to avoid detection. [Link](https://attack.mitre.org/techniques/T1070/)

#### Mitigations
- **Prompt Obfuscation**: Obfuscate system prompts and use dynamic prompt management.
- **Configuration Reviews**: Conduct regular reviews of system configurations to prevent leakage.

---

### [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)
**Description:** Weaknesses in vector representations or embeddings can be exploited to manipulate model outputs or bypass restrictions.

#### MITRE ATT&CK Mapping
- **Data Obfuscation (T1001)**
  - **Tactic:** Command and Control
  - **Technique:** Obfuscating embeddings or vector data to evade detection. [Link](https://attack.mitre.org/techniques/T1001/)

#### Mitigations
- **Embedding Validation**: Implement regular validation and testing of embedding integrity.
- **Adversarial Testing**: Use adversarial techniques to identify and mitigate potential manipulation.

---

### [LLM09:2025 Misinformation](https://genai.owasp.org/)
**Description:** LLMs can generate inaccurate, misleading, or biased information that influences decision-making or public perception.

#### MITRE ATT&CK Mapping
- **Web Service (T1102)**
  - **Tactic:** Command and Control
  - **Technique:** Leveraging LLM-generated misinformation to control the narrative or deceive users. [Link](https://attack.mitre.org/techniques/T1102/)

#### Mitigations
- **Retrieval-Augmented Generation (RAG)**: Apply retrieval-augmented generation techniques for better grounding.
- **Human Oversight**: Use human oversight and cross-verification to ensure factual accuracy.

---

### [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)
**Description:** Uncontrolled resource consumption by LLMs can lead to denial of service (DoS) or other resource-based attacks.

#### MITRE ATT&CK Mapping
- **Endpoint Denial of Service (T1499)**
  - **Tactic:** Impact
  - **Technique:** Exploiting LLM processing to exhaust system resources. [Link](https://attack.mitre.org/techniques/T1499/)

#### Mitigations
- **Rate Limiting**: Implement rate limiting, memory management, and input size restrictions.
- **Load Balancing**: Monitor system performance and apply load balancing for high-volume interactions.

---

This mapping aims to enhance understanding of the relationship between OWASP Top 10 for LLM vulnerabilities and MITRE ATT&CK tactics and techniques, supporting improved security strategies for LLM applications. For more details, visit [OWASP Top 10 for LLM Applications](https://genai.owasp.org) and [MITRE ATT&CK Framework](https://attack.mitre.org/).
