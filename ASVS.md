#  OWASP Top 10 for Large Language Model Applications 2025 Mapped to ASVS


This repo provides a detailed mapping of the vulnerabilities outlined in the [OWASP Top 10 for LLM Applications: 2025](https://genai.owasp.org) to the [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/ASVS/). The goal is to offer developers and security teams a comprehensive view of how to align AI-specific security measures with broader application security standards.

## Overview of Vulnerabilities and ASVS Mapping

| **LLM Vulnerability**                | **ASVS Categories**                       |
|--------------------------------------|------------------------------------------|
| LLM01: Prompt Injection              | Input Validation and Encoding, Integrity Verification |
| LLM02: Sensitive Information Disclosure | Data Protection Requirements, Access Controls |
| LLM03: Supply Chain Vulnerabilities  | Secure Deployment Requirements, Dependency Management |
| LLM04: Data and Model Poisoning      | Data Validation, Machine Learning Security |
| LLM05: Insecure Output Handling      | Output Encoding and Escaping, Secure Processing of Outputs |
| LLM06: Excessive Agency              | Least Privilege Access, Automated Actions |
| LLM07: System Prompt Leakage         | Information Leakage, Secrets Management |
| LLM08: Vector and Embedding Weaknesses | Data Validation and Cleansing, AI Security |
| LLM09: Misinformation                | Data Quality Assurance, Model Performance Validation |
| LLM10: Unbounded Consumption         | Denial of Service Protection, AI Resource Management |

---

## LLM01:2025 - Prompt Injection

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

## LLM02:2025 - Sensitive Information Disclosure

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

## LLM03:2025 - Supply Chain Vulnerabilities

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

## LLM04:2025 - Data and Model Poisoning

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

## LLM05:2025 - Insecure Output Handling

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


This mapping serves as a guide for integrating AI-specific security controls into broader application security standards. By aligning OWASP's Top 10 for LLM Applications with ASVS, organizations can enhance their security posture and ensure the safe deployment of LLMs.

**Next Steps**:
- Prioritize implementation based on risk levels associated with each vulnerability.
- Use automated tools and regular audits to ensure continuous security alignment.
- Participate in the OWASP community to stay updated with evolving security practices for AI applications.

**Further Reading**:
- [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/ASVS/)
- [NIST AI Security Guidelines](https://www.nist.gov/publications/ai-safety)
