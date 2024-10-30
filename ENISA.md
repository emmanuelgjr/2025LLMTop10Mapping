# OWASP Top 10 for LLM Applications 2025 Mapped to ENISA

The rapid adoption of Large Language Models (LLMs) introduces new security vulnerabilities that must be addressed for safe and secure deployment. The OWASP Top 10 for LLM Applications identifies the most critical security vulnerabilities associated with LLMs. This document maps each vulnerability to relevant frameworks and controls outlined by the European Union Agency for Cybersecurity (ENISA). By aligning LLM vulnerabilities with ENISA standards, we aim to assist security professionals in developing secure LLM technology and advancing the safe deployment of LLM applications.

Additionally, this repo provides practical examples, mitigation timelines, severity ratings, and role-specific guidance to help stakeholders prioritize and effectively manage security risks associated with LLM deployments.

## Table of Contents

1. [LLM01:2025 Prompt Injection](https://genai.owasp.org/)
2. [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)
3. [LLM03:2025 Supply Chain Risks](https://genai.owasp.org/)
4. [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)
5. [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)
6. [LLM06:2025 Excessive Agency](https://genai.owasp.org/)
7. [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)
8. [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)
9. [LLM09:2025 Misinformation](https://genai.owasp.org/)
10. [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

---

### LLM0$1:2025 Prompt Injection $2

**Severity Rating:** High

**Description:** $3

- **Real-World Example:** $4

- **Challenges and Lessons Learned:** One of the key challenges in mitigating prompt injection is balancing robust input filtering without overly restricting user interactions. Lessons learned from past incidents show the importance of continuous testing and improving model adaptability.

- **ENISA Mapping:**
  - **ENISA AI Threat Landscape:** Highlights the need for secure model inputs and prevention of unintended model behaviors.
  - **ENISA Guideline:** Focus on hardening input handling and implementing adversarial testing, as emphasized in ENISA’s security-by-design principles.
  - **MITRE ATLAS Techniques:** [AML.T0051.000 - Direct Prompt Injection](https://atlas.mitre.org/techniques/AML.T0051.000), [AML.T0051.001 - Indirect Prompt Injection](https://atlas.mitre.org/techniques/AML.T0051.001)

**Mitigation Strategies:**
$1

- **Timeline for Mitigation:** High-priority, immediate implementation within 3 months.

**Use Case for Mitigation:**
In chatbot applications, ensure that user inputs are sanitized and that responses are filtered to avoid returning unintended results.

**References:**
- [ENISA AI Threat Landscape](https://www.enisa.europa.eu)
- [MITRE ATLAS](https://atlas.mitre.org)

---

### LLM01:2025 Prompt Injection

### LLM02:2025 Sensitive Information Disclosure

**Description:** LLMs may unintentionally reveal sensitive information such as PII, proprietary data, or internal configuration details.

- **Real-World Example:** LLMs accidentally generating names, addresses, or financial details due to training data exposure.

- **ENISA Mapping:**
  - **ENISA’s Guidelines on PII Protection:** Emphasizes data minimization and robust access controls to prevent leaks.
  - **ENISA's Secure Data Handling:** Implements federated learning and differential privacy to protect data integrity.

**Mitigation Strategies:**
- Implement data sanitization techniques.
- Use strict access controls and federated learning to limit centralized data exposure.

**Use Case for Mitigation:**
In customer support systems, use federated learning to train LLMs on user data without exposing sensitive customer information.

**References:**
- [OWASP API Security: Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)
- [ENISA Data Protection Guideline](https://www.enisa.europa.eu)

---

### LLM03:2025 Supply Chain Risks Supply Chain Risks

**Description:** LLMs can inherit vulnerabilities from third-party models, APIs, or datasets, leading to compromised integrity.

- **Real-World Example:** Dependency on third-party models or datasets with known vulnerabilities that propagate into the LLM application.

- **ENISA Mapping:**
  - **ENISA Supply Chain Guidelines:** Emphasizes third-party risk management, software bill of materials (SBOM), and integrity verification of external dependencies.

**Mitigation Strategies:**
- Perform supply chain audits and secure model development lifecycle practices.
- Use digital signatures for verifying third-party data and models.

**References:**
- [ENISA Supply Chain Security](https://www.enisa.europa.eu)

---

### LLM04:2025 Data and Model Poisoning Data and Model Poisoning

**Description:** Attackers manipulate training data or model parameters to alter LLM outputs, leading to biases or harmful behavior.

- **ENISA Mapping:**
  - **ENISA AI Security:** Promotes the use of adversarial detection techniques and regular model retraining to counter poisoning risks.

**Mitigation Strategies:**
- Use federated learning to reduce exposure risks.
- Conduct adversarial training to detect and counteract data poisoning.

**References:**
- [ENISA AI Security Framework](https://www.enisa.europa.eu)

---

### LLM05:2025 Insecure Output Handling Insecure Output Handling

**Description:** Output from LLMs can leak sensitive information or be manipulated to execute malicious commands.

- **ENISA Mapping:**
  - **ENISA Output Security Recommendations:** Emphasizes output validation and secure parsing mechanisms to avoid unintended leaks.

**Mitigation Strategies:**
- Implement output validation.
- Restrict sensitive output categories through predefined filters.

**References:**
- [ENISA Output Security](https://www.enisa.europa.eu)

---

### LLM06:2025 Excessive Agency Excessive Agency

**Description:** LLMs with excessive autonomy can execute unauthorized actions or escalate privileges.

- **ENISA Mapping:**
  - **ENISA Autonomy Control Guidelines:** Recommends implementing strict permission controls and human-in-the-loop mechanisms for high-risk actions.

**Mitigation Strategies:**
- Enforce privilege control.
- Limit model capabilities through role-specific configurations.

**References:**
- [ENISA Autonomy Guidelines](https://www.enisa.europa.eu)

---

### LLM07:2025 System Prompt Leakage System Prompt Leakage

**Description:** System prompts or instructions may be exposed, allowing attackers to manipulate LLMs.

- **ENISA Mapping:**
  - **ENISA Configuration Security:** Ensures system prompts are securely concealed and protected against unauthorized access.

**Mitigation Strategies:**
- Implement robust system preamble protection.
- Regularly audit system configurations to ensure prompt security.

**References:**
- [ENISA Configuration Security](https://www.enisa.europa.eu)

---

### LLM08:2025 Vector and Embedding Weaknesses Vector and Embedding Weaknesses

**Description:** Vulnerabilities in vector embeddings can lead to model manipulation or inference attacks.

- **ENISA Mapping:**
  - **ENISA Embedding Security:** Promotes secure handling of vectors and embeddings to prevent unauthorized inference.

**Mitigation Strategies:**
- Use encrypted embeddings and apply differential privacy to embeddings.

**References:**
- [ENISA Embedding Security](https://www.enisa.europa.eu)

---

### LLM09:2025 Misinformation Misinformation

**Description:** LLMs can generate false information, leading to disinformation campaigns or incorrect outputs.

- **ENISA Mapping:**
  - **ENISA’s Disinformation Mitigation:** Recommends using retrieval-augmented generation (RAG), human oversight, and cross-verification.

**Mitigation Strategies:**
- Use cross-verification and implement retrieval-augmented generation to enhance output reliability.

**References:**
- [ENISA Disinformation Mitigation](https://www.enisa.europa.eu)

---

### LLM10:2025 Unbounded Consumption Unbounded Consumption

**Description:** Unrestricted resource usage by LLMs can lead to denial-of-service (DoS) attacks or resource depletion.

- **ENISA Mapping:**
  - **ENISA Resource Control:** Focuses on rate limiting, quota management, and capacity planning to prevent overconsumption.

**Mitigation Strategies:**
- Implement rate limiting and quota management.
- Use monitoring tools to detect and prevent excessive consumption.

**References:**
- [ENISA Resource Control](https://www.enisa.europa.eu)

---

## Stakeholder Guidance

### For Developers
$1
- Utilize threat modeling tools like Microsoft Threat Modeling Tool to assess potential attack vectors specific to LLMs.

### For Security Professionals
$1
- Consider using AI-specific risk assessment tools to identify new emerging threats.

### For Decision-Makers
$1
- Allocate budget for security teams to focus on regular assessments of third-party dependencies and supply chain risks.

---

## Glossary

- **LLM (Large Language Model):** A type of artificial intelligence model designed to understand and generate natural language.
- **Federated Learning:** A machine learning technique that trains an algorithm across multiple decentralized devices without exchanging data.
- **Differential Privacy:** A system that allows the extraction of useful information from datasets while protecting individual privacy.
- **Retrieval-Augmented Generation (RAG):** A technique that combines retrieval of external knowledge with generation capabilities to produce accurate outputs.

---

## Versioning and Update Policy

$1

To ensure that the document remains up to date, we also plan to include quarterly updates addressing emerging threats and changes in ENISA's guidelines.

## Call for Community Collaboration

We encourage the security community to participate in keeping this document updated. If you have suggestions, additions, or corrections, please contribute to the project on our [GitHub repository](https://github.com/OWASP/LLM-Top10). Your contributions are essential to maintaining a robust and comprehensive resource for securing LLM applications.
