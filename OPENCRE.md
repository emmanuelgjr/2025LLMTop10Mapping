# OWASP Top 10 for Large Language Model Applications 2025 Mapped to OPENCRE

This repo mapping aligns the OWASP Top 10 for LLM Apps 2025 vulnerabilities with the [**OPENCRE (Open Common Requirement Enumeration)**](https://opencre.org/) framework, linking potential threats to appropriate mitigation measures.


| **Vulnerability**                      | **OPENCRE Mappings**                                                                                   |
|----------------------------------------|--------------------------------------------------------------------------------------------------------|
| LLM01: Prompt Injection           | [CRE-1713: Injection Attacks](https://opencre.org/cre/1713), [CRE-1312: Input Validation](https://opencre.org/cre/1312), [CRE-1320: Command Injection](https://opencre.org/cre/1320) |
| LLM02: Sensitive Information Disclosure | [CRE-1365: Sensitive Data Exposure](https://opencre.org/cre/1365), [CRE-1512: Access Control](https://opencre.org/cre/1512), [CRE-1320: Privacy Controls](https://opencre.org/cre/1320) |
| LLM03: Supply Chain Risks          | [CRE-1410: Supply Chain Security](https://opencre.org/cre/1410), [CRE-1720: Software Dependency Management](https://opencre.org/cre/1720), [CRE-1335: Data Integrity](https://opencre.org/cre/1335) |
| LLM04: Data and Model Poisoning    | [CRE-1623: Data Poisoning](https://opencre.org/cre/1623), [CRE-1335: Model Integrity](https://opencre.org/cre/1335), [CRE-1713: Adversarial Attacks](https://opencre.org/cre/1713) |
| LLM05: Insecure Output Handling    | [CRE-1365: Output Handling](https://opencre.org/cre/1365), [CRE-1512: Response Filtering](https://opencre.org/cre/1512), [CRE-1720: Context Validation](https://opencre.org/cre/1720) |
| LLM06: Excessive Agency            | [CRE-1625: Excessive Functionality](https://opencre.org/cre/1625), [CRE-1512: Access Control](https://opencre.org/cre/1512), [CRE-1410: Privilege Management](https://opencre.org/cre/1410) |
| LLM07: System Prompt Leakage       | [CRE-1720: System Prompt Security](https://opencre.org/cre/1720), [CRE-1512: Data Leakage Prevention](https://opencre.org/cre/1512), [CRE-1365: Configuration Management](https://opencre.org/cre/1365) |
| LLM08: Vector and Embedding Weaknesses | [CRE-1335: Vector Manipulation](https://opencre.org/cre/1335), [CRE-1713: Embedding Risks](https://opencre.org/cre/1713), [CRE-1320: Adversarial Attacks](https://opencre.org/cre/1320) |
| LLM09: Misinformation              | [CRE-1410: Misinformation Control](https://opencre.org/cre/1410), [CRE-1335: Truth Verification](https://opencre.org/cre/1335), [CRE-1623: Fact-checking Mechanisms](https://opencre.org/cre/1623) |
| LLM10: Unbounded Consumption       | [CRE-1720: Resource Management](https://opencre.org/cre/1720), [CRE-1512: Rate Limiting](https://opencre.org/cre/1512), [CRE-1365: Consumption Control](https://opencre.org/cre/1365) |


---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org)

- **Description:** Occurs when crafted inputs alter LLM behaviour or outputs, bypassing safety measures and enabling unauthorized actions.
- **Impact:** Unauthorized data access, sensitive information exposure, and biased decision-making.
- **OPENCRE Mapping:**
  - [CRE-1713: Injection Attacks](https://opencre.org/cre/1713)
  - [CRE-1312: Input Validation](https://opencre.org/cre/1312)
  - [CRE-1320: Command Injection](https://opencre.org/cre/1320)

**Mitigation Strategies:**
- Constrain model behaviour by enforcing strict response rules within prompts.
- Input & Output Filtering: Use semantic filters to handle suspicious content.
- Adversarial Testing: Conduct regular penetration testing to identify injection risks.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org)

- **Description:** The model may expose sensitive data, including PII, business secrets, or proprietary algorithms.
- **Impact:** Data leaks, privacy violations, and IP breaches.
- **OPENCRE Mapping:**
  - [CRE-1365: Sensitive Data Exposure](https://opencre.org/cre/1365)
  - [CRE-1512: Access Control](https://opencre.org/cre/1512)
  - [CRE-1320: Privacy Controls](https://opencre.org/cre/1320)

**Mitigation Strategies:**
- Data Sanitization: Scrub or mask sensitive data inputs.
- Implement strict access controls using least privilege access.
- Decentralize training data through federated learning to minimize risks.

---

## [LLM03:2025 Supply Chain Risks](https://genai.owasp.org)

- **Description:** Vulnerabilities from third-party components, data sources, or model dependencies.
- **Impact:** Compromise of data integrity, injection of malicious data, and cascading failures.
- **OPENCRE Mapping:**
  - [CRE-1410: Supply Chain Security](https://opencre.org/cre/1410)
  - [CRE-1720: Software Dependency Management](https://opencre.org/cre/1720)
  - [CRE-1335: Data Integrity](https://opencre.org/cre/1335)

**Mitigation Strategies:**
- Source Validation: Vet third-party libraries and data sources thoroughly.
- Dependency Isolation: Use sandboxing techniques to isolate critical components.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org)

- **Description:** Altered training data or model parameters, causing incorrect outputs or malicious behaviour.
- **Impact:** Deceptive responses, compromised decision-making, and model degradation.
- **OPENCRE Mapping:**
  - [CRE-1623: Data Poisoning](https://opencre.org/cre/1623)
  - [CRE-1335: Model Integrity](https://opencre.org/cre/1335)
  - [CRE-1713: Adversarial Attacks](https://opencre.org/cre/1713)

**Mitigation Strategies:**
- Regular Model Audits: Assess training datasets for anomalies.
- Differential Privacy: Add noise to data to protect individual data points.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org)

- **Description:** Outputs not properly sanitized may lead to unauthorized disclosures or actions.
- **Impact:** Data leakage, unintended command execution, or policy violations.
- **OPENCRE Mapping:**
  - [CRE-1365: Output Handling](https://opencre.org/cre/1365)
  - [CRE-1512: Response Filtering](https://opencre.org/cre/1512)
  - [CRE-1720: Context Validation](https://opencre.org/cre/1720)

**Mitigation Strategies:**
- Define Output Formats: Use predefined formats for responses.
- Output Validation: Apply validation mechanisms to ensure safe outputs.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org)

- **Description:** LLMs executing privileged actions beyond the intended scope.
- **Impact:** Unauthorized access, security breaches, and operational disruptions.
- **OPENCRE Mapping:**
  - [CRE-1625: Excessive Functionality](https://opencre.org/cre/1625)
  - [CRE-1512: Access Control](https://opencre.org/cre/1512)
  - [CRE-1410: Privilege Management](https://opencre.org/cre/1410)

**Mitigation Strategies:**
- Human-in-the-Loop: Require human approval for high-risk actions.
- Least Privilege Access: Limit model permissions.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org)

- **Description:** Exposure of internal prompts or configurations, leading to potential exploits.
- **Impact:** System configuration leaks, unauthorized access, or privilege escalation.
- **OPENCRE Mapping:**
  - [CRE-1720: System Prompt Security](https://opencre.org/cre/1720)
  - [CRE-1512: Data Leakage Prevention](https://opencre.org/cre/1512)
  - [CRE-1365: Configuration Management](https://opencre.org/cre/1365)

**Mitigation Strategies:**
- System Preamble Concealment: Restrict access to system configurations.
- Prompt Isolation: Keep system prompts separate from user inputs.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org)

- **Description:** Flaws in embeddings or vector representations may lead to inaccurate responses or vulnerabilities.
- **Impact:** Malicious embedding attacks, vector manipulation, and bias introduction.
- **OPENCRE Mapping:**
  - [CRE-1335: Vector Manipulation](https://opencre.org/cre/1335)
  - [CRE-1713: Embedding Risks](https://opencre.org/cre/1713)
  - [CRE-1320: Adversarial Attacks](https://opencre.org/cre/1320)

**Mitigation Strategies:**
- Embedding Isolation: Use separate embeddings for critical operations.
- Vector Verification: Validate vector inputs and outputs.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org)

- **Description:** LLMs generating false or misleading information.
- **Impact:** Spread of misinformation, credibility loss, and incorrect decision-making.
- **OPENCRE Mapping:**
  - [CRE-1410: Misinformation Control](https://opencre.org/cre/1410)
  - [CRE-1335: Truth Verification](https://opencre.org/cre/1335)
  - [CRE-1623: Fact-checking Mechanisms](https://opencre.org/cre/1623)

**Mitigation Strategies:**
- Cross-Verification: Implement multi-source validation.
- Human Oversight: Include manual review of outputs.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org)

- **Description:** LLMs consuming excessive resources, leading to performance issues or denial-of-service.
- **Impact:** Resource exhaustion, slow response times, or service outages.
- **OPENCRE Mapping:**
  - [CRE-1720: Resource Management](https://opencre.org/cre/1720)
  - [CRE-1512: Rate Limiting](https://opencre.org/cre/1512)
  - [CRE-1365: Consumption Control](https://opencre.org/cre/1365)

**Mitigation Strategies:**
- Rate Limiting: Apply restrictions to input requests.
- Resource Monitoring: Implement resource utilization alerts.

---

The OWASP Top 10 for Large Language Model Applications provides a comprehensive guide for identifying and mitigating the most critical risks associated with LLM deployments, mapping these risks to the OPENCRE framework, allows organizations to better understand the necessary security controls and implement strategies to protect against vulnerabilities specific to LLM systems. Proactive measures, such as thorough risk assessment, consistent validation, and robust security controls, are essential for mitigating the evolving threats in the LLM landscape.

