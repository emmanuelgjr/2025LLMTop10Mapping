#  OWASP Top 10 for Large Language Model Applications 2025 Mapped to ASVS


This repo provides a detailed mapping of the vulnerabilities outlined in the [OWASP Top 10 for LLM Applications: 2025](https://genai.owasp.org) to the [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/ASVS/). The goal is to offer developers and security teams a comprehensive view of how to align AI-specific security measures with broader application security standards.

| **Vulnerability**                         | **Risk Level** | **ASVS Categories**                                  | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|------------|--------------------------------------------------|----------------------------------------|-----------------------------------------------------|
| LLM01:2025 Prompt Injection           | High       | Input Validation and Encoding, Integrity Verification | Unauthorized access, data leakage      | Strict input validation, enforce prompt integrity    |
| LLM02:2025 Sensitive Information Disclosure | High       | Data Protection Requirements, Access Controls     | Exposure of sensitive information      | Data masking, access controls                       |
| LLM03:2025 Supply Chain Vulnerabilities | Medium     | Secure Deployment Requirements, Dependency Management | Malicious components, unverified dependencies | Regular audits, use of composition analysis tools   |
| LLM04:2025 Data and Model Poisoning   | High       | Data Validation, Machine Learning Security       | Compromised training data, incorrect outputs | Data audits, secure data pipelines                  |
| LLM05:2025 Insecure Output Handling   | Medium     | Output Encoding and Escaping, Secure Processing of Outputs | Data leakage, injection vulnerabilities | Output filtering, output format definitions         |
| LLM06:2025 Excessive Agency           | Medium     | Least Privilege Access, Automated Actions        | Unintended autonomous actions          | Enforce least privilege, human approval for high-risk actions |
| LLM07:2025 System Prompt Leakage      | Medium     | Information Leakage, Secrets Management          | System prompt exposure                 | Conceal system prompts, implement secure configuration practices |
| LLM08:2025 Vector and Embedding Weaknesses | Medium     | Data Validation and Cleansing, AI Security       | Biased or malicious outputs            | Adversarial testing, secure vector databases         |
| LLM09:2025 Misinformation             | Medium     | Data Quality Assurance, Model Performance Validation | Inaccurate or misleading content      | Cross-verification, human oversight                  |
| LLM10:2025 Unbounded Consumption      | Low        | Denial of Service Protection, AI Resource Management | Excessive resource usage, denial of service | Rate-limiting, load balancing                       |


---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Prompt injection occurs when user inputs alter the behaviour of the LLM, potentially causing unauthorized access or manipulation.

- **ASVS Mapping**:
  - **ASVS 5.3: Input Validation and Encoding**: Implement strict input validation to prevent manipulation of LLM prompts.
  - **ASVS 8.1: Integrity Verification**: Enforce verification of prompts to maintain integrity.

- **Mitigation Strategies**:
  1. Constrain model behaviour with strict role definitions.
  2. Validate expected output formats using deterministic code.
- **Practical Example**:
  - If an LLM is used to generate responses for customer support, use predefined response templates and validate user inputs rigorously.

- **Related Resources**:
  - [MITRE ATLAS - LLM Prompt Injection: Direct](https://atlas.mitre.org/techniques/AML.T0051.000)
  - [OWASP Testing Guide - Input Validation](https://owasp.org/www-project-web-security-testing-guide/)

**Key Risks**: Unauthorized access, data leakage

**Top Mitigation Steps**: Strict input validation, enforce prompt integrity

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Risks arise when LLMs expose sensitive data, such as PII or proprietary information.

- **ASVS Mapping**:
  - **ASVS 1.5: Data Protection Requirements**: Implement data masking and sanitization to protect sensitive information.
  - **ASVS 4.3: Access Controls**: Enforce access controls to minimize unauthorized data access.

- **Mitigation Strategies**:
  1. Integrate data sanitization techniques.
  2. Apply federated learning and differential privacy measures.

- **Practical Example**:
  - Avoid allowing LLMs to generate outputs involving personal identifiers without strict access control.

- **Related Resources**:
  - [ASVS 4.1: Sensitive Data Handling](https://owasp.org/ASVS/)
  - [OWASP API Security Top 10 - Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)

**Key Risks**: Exposure of sensitive information

**Top Mitigation Steps**: Data masking, access controls

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Weak supply chain security can lead to vulnerabilities in LLM implementations.

- **ASVS Mapping**:
  - **ASVS 1.9: Secure Deployment Requirements**: Ensure secure integration of third-party components.
  - **ASVS 9.5: Dependency Management**: Regularly audit and manage dependencies to prevent supply chain attacks.

- **Mitigation Strategies**:
  1. Perform regular audits of third-party libraries.
  2. Use software composition analysis tools.

- **Practical Example**:
  - Regularly update and audit the libraries used for LLM deployments.

- **Related Resources**:
  - [OWASP Software Component Verification Standard (SCVS)](https://owasp.org/scvs/)

**Key Risks**: Malicious components, unverified dependencies

**Top Mitigation Steps**: Regular audits, use of composition analysis tools

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data poisoning occurs when malicious inputs are used to alter the model’s training data, leading to harmful outputs.

- **ASVS Mapping**:
  - **ASVS 8.2: Data Validation**: Validate training data to ensure integrity.
  - **ASVS 10.4: Machine Learning Security**: Implement safeguards for model integrity and security.

- **Mitigation Strategies**:
  1. Perform regular data audits to detect anomalies.
  2. Use secure data pipelines with encryption.

- **Practical Example**:
  - Monitor data ingestion pipelines to detect and mitigate potentially poisoned inputs.

- **Related Resources**:
  - [NIST ML Security - Model Poisoning](https://www.nist.gov/publications/ml-security)

**Key Risks**: Compromised training data, incorrect outputs

**Top Mitigation Steps**: Data audits, secure data pipelines

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: LLMs may generate outputs that disclose sensitive information or contain unintended commands.

- **ASVS Mapping**:
  - **ASVS 5.7: Output Encoding and Escaping**: Implement output encoding to prevent unintended actions.
  - **ASVS 8.6: Secure Processing of Outputs**: Ensure output validation to mitigate risks.

- **Mitigation Strategies**:
  1. Apply output filtering and validation.
  2. Define strict output formats to prevent harmful data leakage.

- **Practical Example**:
  - Sanitize LLM outputs to ensure they do not contain HTML that could lead to XSS vulnerabilities.

- **Related Resources**:
  - [OWASP Output Encoding Cheat Sheet](https://owasp.org/cheatsheets/Output_Encoding_Cheat_Sheet.html)

**Key Risks**: Data leakage, injection vulnerabilities

**Top Mitigation Steps**: Output filtering, output format definitions

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to unintended actions taken by LLMs, such as making autonomous decisions beyond their intended scope.

- **ASVS Mapping**:
  - **ASVS 4.4: Least Privilege Access**: Limit model permissions to necessary functions only.
  - **ASVS 10.3: Automated Actions**: Implement human-in-the-loop checks for high-risk operations.

- **Mitigation Strategies**:
  1. Enforce privilege control and least privilege principles.
  2. Require human approval for high-risk actions.

- **Practical Example**:
  - Limit an LLM’s access to databases and require human review for any action that could modify critical data.

- **Related Resources**:
  - [NIST Principles for AI Safety](https://www.nist.gov/publications/ai-safety)

**Key Risks**: Unintended autonomous actions

**Top Mitigation Steps**: Enforce least privilege, human approval for high-risk actions

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompts can be exposed, allowing attackers to manipulate model behaviour.
- **ASVS Mapping**:
  - **ASVS 7.1: Information Leakage**: Prevent exposure of system prompts through secure configurations.
  - **ASVS 9.1: Secrets Management**: Store system prompts securely to prevent leakage.

- **Mitigation Strategies**:
  1. Conceal system prompts to prevent unauthorized access.
  2. Implement secure configuration practices.

- **Practical Example**:
  - Use secure storage solutions for system prompts and restrict access to only authorized personnel.

- **Related Resources**:
  - [OWASP Testing Guide - Security Misconfiguration](https://owasp.org/www-project-web-security-testing-guide/)

**Key Risks**: System prompt exposure

**Top Mitigation Steps**: Conceal system prompts, implement secure configuration practices

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Embeddings can be manipulated to produce biased or malicious outputs.

- **ASVS Mapping**:
  - **ASVS 8.4: Data Validation and Cleansing**: Validate embeddings to prevent adversarial attacks.
  - **ASVS 10.5: AI Security**: Implement embedding security measures.

- **Mitigation Strategies**:
  1. Apply adversarial testing to embeddings.
  2. Use secure vector databases.

- **Practical Example**:
  - Validate and cleanse embedding vectors to ensure they do not contain unintended biases or vulnerabilities.

- **Related Resources**:
  - [MITRE ATLAS - Embedding Manipulation](https://atlas.mitre.org/techniques/AML.T0052)

**Key Risks**: Biased or malicious outputs

**Top Mitigation Steps**: Adversarial testing, secure vector databases

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation vulnerabilities arise when LLMs produce inaccurate or misleading content.

- **ASVS Mapping**:
  - **ASVS 9.3: Data Quality Assurance**: Ensure data accuracy and quality to prevent misinformation.
  - **ASVS 10.2: Model Performance Validation**: Regularly validate model performance to reduce misinformation risks.

- **Mitigation Strategies**:
  1. Implement cross-verification and human oversight for high-risk outputs.
  2. Use retrieval-augmented generation to provide accurate responses.

- **Practical Example**:
  - Cross-check the LLM's responses with authoritative data sources for high-risk domains.

- **Related Resources**:
  - [NIST Misinformation Detection Guidelines](https://www.nist.gov/publications/misinformation-detection)

**Key Risks**: Inaccurate or misleading content

**Top Mitigation Steps**: Cross-verification, human oversight

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Unbounded consumption refers to excessive resource usage by LLMs, leading to potential denial of service.

- **ASVS Mapping**:
  - **ASVS 7.2: Denial of Service Protection**: Implement resource throttling and monitoring.
  - **ASVS 10.1: AI Resource Management**: Manage AI resources to prevent overconsumption.

- **Mitigation Strategies**:
  1. Apply rate-limiting and load balancing.
  2. Monitor AI workloads to prevent resource exhaustion.

- **Practical Example**:
  - Implement rate-limiting for API access to prevent excessive requests from overwhelming the system.

- **Related Resources**:
  - [OWASP Rate Limiting Cheat Sheet](https://owasp.org/cheatsheets/Rate_Limiting_Cheat_Sheet.html)

**Key Risks**: Excessive resource usage, denial of service

**Top Mitigation Steps**: Rate-limiting, load balancing

---

This mapping serves as a guide for integrating AI-specific security controls into broader application security standards. By aligning OWASP's Top 10 for LLM Applications with ASVS, organizations can enhance their security posture and ensure the safe deployment of LLMs.

**Next Steps**:
- Prioritize implementation based on risk levels associated with each vulnerability.
- Use automated tools and regular audits to ensure continuous security alignment.
- Participate in the OWASP community to stay updated with evolving security practices for AI applications.

**Further Reading**:
- [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/ASVS/)
- [NIST AI Security Guidelines](https://www.nist.gov/publications/ai-safety)
