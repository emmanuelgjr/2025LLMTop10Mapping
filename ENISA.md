# OWASP Top 10 for LLM Applications 2025 Mapped to ENISA

This repo maps each vulnerability to relevant frameworks and controls outlined by the [**European Union Agency for Cybersecurity (ENISA)**](https://www.enisa.europa.eu/). By aligning LLM vulnerabilities with ENISA standards, we aim to assist security professionals in developing secure LLM technology and advancing the safe deployment of LLM applications.

Additionally, it provides practical examples, mitigation timelines, severity ratings, and role-specific guidance to help stakeholders prioritize and effectively manage security risks associated with LLM deployments.

| **Vulnerability**                         | **Severity Rating** | **ENISA Mapping and Description**                                                                                                                                                                                                                             | **Mitigation Techniques**                          |
|---------------------------------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|
| LLM01:2025 Prompt Injection           | High           | [ENISA AI Threat Landscape](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2024): Highlights the need for secure model inputs. [ENISA Secure Development Principles](https://www.enisa.europa.eu/publications/guideline-on-software-security): Input validation. | Input filtering, adversarial testing          |
| LLM02:2025 Sensitive Information Disclosure | High      | [ENISA’s Guidelines on PII Protection](https://www.enisa.europa.eu): Emphasizes data minimization and access control. [ENISA's Secure Data Handling](https://www.enisa.europa.eu): Implements federated learning, differential privacy.                                                           | Data sanitization, access control              |
| LLM03:2025 Supply Chain Risks         | Medium         | [ENISA Supply Chain Guidelines](https://www.enisa.europa.eu): Emphasizes third-party risk management, software bill of materials (SBOM).                                                                                                                                                          | Supply chain audits, digital signatures        |
| LLM04:2025 Data and Model Poisoning   | High           | [ENISA AI Security](https://www.enisa.europa.eu): Recommends adversarial detection techniques and model retraining.                                                                                                                                                                                | Federated learning, adversarial training       |
| LLM05:2025 Insecure Output Handling   | Medium         | [ENISA Output Security Recommendations](https://www.enisa.europa.eu): Emphasizes output validation and secure parsing mechanisms.                                                                                                                                                                 | Output validation, predefined filters          |
| LLM06:2025 Excessive Agency           | Medium         | [ENISA Autonomy Control Guidelines](https://www.enisa.europa.eu): Recommends strict permission controls and human-in-the-loop mechanisms for high-risk actions.                                                                                                                                    | Privilege control, human oversight             |
| LLM07:2025 System Prompt Leakage      | High           | [ENISA Configuration Security](https://www.enisa.europa.eu): Ensures system prompts are concealed and protected from unauthorized access.                                                                                                                                                         | Preamble protection, system configuration audit|
| LLM08:2025 Vector and Embedding Weaknesses | Medium    | [ENISA Embedding Security](https://www.enisa.europa.eu): Promotes secure handling of vectors to prevent unauthorized inference.                                                                                                                                                                   | Encrypted embeddings, differential privacy     |
| LLM09:2025 Misinformation             | High           | [ENISA’s Disinformation Mitigation](https://www.enisa.europa.eu): Recommends retrieval-augmented generation (RAG) and human oversight.                                                                                                                                                            | Cross-verification, retrieval-augmented generation (RAG)  |
| LLM10:2025 Unbounded Consumption      | Medium         | [ENISA Resource Control](https://www.enisa.europa.eu): Focuses on rate limiting, quota management, and capacity planning to prevent overconsumption.                                                                                                                                               | Rate limiting, resource monitoring             |



---

### [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

**Severity Rating:** High

**Description:** Prompt injection occurs when an attacker manipulates the model's prompt to alter its behaviour in unintended ways. This vulnerability often involves user inputs bypassing the intended guardrails or safety measures to make the model generate harmful or unexpected outputs.

- **Real-World Example:** An attacker provides a cleverly crafted input to a chatbot to elicit sensitive information or circumvent the model's filtering mechanisms, leading to outputs containing inappropriate or harmful content.

- **Challenges and Lessons Learned:** One of the key challenges in mitigating prompt injection is balancing robust input filtering without overly restricting user interactions. Lessons learned from past incidents show the importance of continuous testing and improving model adaptability.

- **ENISA Mapping:**
  - **ENISA AI Threat Landscape:** Highlights the need for secure model inputs and prevention of unintended model behaviours.
  - **ENISA Secure Development Principles:** Recommends implementing input validation and adversarial testing.

**Relevant Links:**
- [ENISA AI Threat Landscape Overview](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2024)
- [MITRE ATLAS Techniques Overview](https://atlas.mitre.org)

**Mitigation Strategies:**
- Constrain model behaviour through context adherence.
- Filter inputs and outputs to limit prompt injection attacks.
- Implement regular penetration testing and adversarial simulations.

**Timeline for Mitigation:** High-priority, immediate implementation within 3 months.

**Use Case for Mitigation:** In chatbot applications, ensure that user inputs are sanitized and that responses are filtered to avoid returning unintended results.

**References:**
- [ENISA AI Threat Landscape](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2024)
- [MITRE ATLAS](https://atlas.mitre.org)

---

### [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

**Severity Rating:** High

**Description:** Sensitive information disclosure occurs when LLMs unintentionally reveal sensitive details such as Personally Identifiable Information (PII), proprietary data, or internal configuration due to inappropriate training data or lack of filtering mechanisms.

- **Real-World Example:** LLMs accidentally generate names, addresses, or financial details due to training data exposure.

- **Challenges and Lessons Learned:** Sensitive information disclosure is challenging due to the risk of exposing PII or confidential data inadvertently learned during training. Lessons learned highlight the need for strong data governance and privacy controls.

- **ENISA Mapping:**
  - **ENISA’s Guidelines on PII Protection:** Emphasizes data minimization and robust access controls to prevent leaks.
  - **ENISA's Secure Data Handling:** Implements federated learning and differential privacy to protect data integrity.

**Relevant Links:**
- [OWASP API Security: Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)
- [ENISA Data Protection Guideline](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Implement data sanitization techniques.
- Use strict access controls and federated learning to limit centralized data exposure.

**Timeline for Mitigation:** High-priority, immediate implementation within 3-6 months.

**Use Case for Mitigation:** In customer support systems, use federated learning to train LLMs on user data without exposing sensitive customer information.

**References:**
- [OWASP API Security: Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)
- [ENISA Data Protection Guideline](https://www.enisa.europa.eu)

---

### [LLM03:2025 Supply Chain Risks](https://genai.owasp.org/)

**Severity Rating:** Medium

**Description:** LLMs can inherit vulnerabilities from third-party models, APIs, or datasets, leading to compromised integrity. Supply chain risks affect LLMs due to dependencies on external sources and models, which may introduce security gaps or malicious modifications.

- **Real-World Example:** Dependency on third-party models or datasets with known vulnerabilities that propagate into the LLM application.

- **Challenges and Lessons Learned:** The complexity of managing supply chain risks for LLMs is due to the reliance on third-party models, data sources, and libraries. It is critical to implement a rigorous vetting process for dependencies to minimize risks.

- **ENISA Mapping:**
  - **ENISA Supply Chain Guidelines:** Emphasizes third-party risk management, software bill of materials (SBOM), and integrity verification of external dependencies.

**Relevant Links:**
- [ENISA Supply Chain Security](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Perform supply chain audits and secure model development lifecycle practices.
- Use digital signatures for verifying third-party data and models.

**Timeline for Mitigation:** Medium-priority, implementation within 6-12 months.

**Use Case for Mitigation:** Ensure supply chain audits are conducted and that every third-party dependency is vetted and regularly monitored.

**References:**
- [ENISA Supply Chain Security](https://www.enisa.europa.eu)

---

### [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

**Severity Rating:** High

**Description:** Data and model poisoning occurs when attackers manipulate the training data or model parameters to alter LLM outputs, leading to biased, harmful, or unintended behaviour. This risk undermines the integrity of LLM-generated results.

- **Real-World Example:** Attackers introduce malicious data into training sets to alter the behaviour of the LLM in harmful ways, such as injecting biases.

- **Challenges and Lessons Learned:** Ensuring data integrity in LLM training pipelines is critical. Lessons learned emphasize the need for robust validation and monitoring of training data.

- **ENISA Mapping:**
  - **ENISA AI Security:** Promotes the use of adversarial detection techniques and regular model retraining to counter poisoning risks.

**Relevant Links:**
- [ENISA AI Security Framework](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Use federated learning to reduce exposure risks.
- Conduct adversarial training to detect and counteract data poisoning.

**Timeline for Mitigation:** High-priority, immediate implementation within 3 months.

**Use Case for Mitigation:** Regularly audit and validate training datasets to detect and mitigate poisoning attempts.

**References:**
- [ENISA AI Security Framework](https://www.enisa.europa.eu)

---

### [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

**Severity Rating:** Medium

**Description:** Insecure output handling occurs when LLM-generated outputs inadvertently contain sensitive information or when outputs can be manipulated to execute harmful commands. Such vulnerabilities can lead to privacy breaches or unintended model actions.

- **Real-World Example:** Generated outputs that inadvertently contain sensitive data or provide a path for executing unintended commands.

- **Challenges and Lessons Learned:** Handling output securely is challenging as LLMs may generate unpredictable responses. Lessons learned suggest the importance of implementing output validation mechanisms.

- **ENISA Mapping:**
  - **ENISA Output Security Recommendations:** Emphasizes output validation and secure parsing mechanisms to avoid unintended leaks.

**Relevant Links:**
- [ENISA Output Security](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Implement output validation.
- Restrict sensitive output categories through predefined filters.

**Timeline for Mitigation:** Medium-priority, implementation within 6 months.

**Use Case for Mitigation:** Ensure that output is validated and sensitive information is filtered before any external communication.

**References:**
- [ENISA Output Security](https://www.enisa.europa.eu)

---

### [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

**Severity Rating:** Medium

**Description:** Excessive agency occurs when LLMs are granted too much autonomy, leading to actions beyond their intended scope, including unauthorized API calls or privilege escalations. This creates risks related to unintended automated behaviours and unauthorized access.

- **Real-World Example:** LLMs autonomously generating actions beyond their intended scope, such as unauthorized API calls.

- **Challenges and Lessons Learned:** Controlling the autonomy of LLMs is complex, particularly when models are integrated with other systems. Lessons learned highlight the need for role-based access control and human oversight.

- **ENISA Mapping:**
  - **ENISA Autonomy Control Guidelines:** Recommends implementing strict permission controls and human-in-the-loop mechanisms for high-risk actions.

**Relevant Links:**
- [ENISA Autonomy Guidelines](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Enforce privilege control.
- Limit model capabilities through role-specific configurations.

**Timeline for Mitigation:** Medium-priority, implementation within 6-9 months.

**Use Case for Mitigation:** Implement strict role-based permissions and ensure human review of high-risk actions taken by LLMs.

**References:**
- [ENISA Autonomy Guidelines](https://www.enisa.europa.eu)

---

### [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

**Severity Rating:** High

**Description:** System prompt leakage occurs when attackers gain access to system-level prompts or internal instructions, allowing them to manipulate LLM behaviours or extract sensitive configurations. Such leakage can compromise the security and integrity of the LLM system.

- **Real-World Example:** Attackers are able to access system-level prompts or instructions, enabling them to manipulate LLM behaviour.

- **Challenges and Lessons Learned:** Preventing prompt leakage requires careful handling of system-level configurations. Lessons learned stress the importance of robust system protection and prompt encryption.

- **ENISA Mapping:**
  - **ENISA Configuration Security:** Ensures system prompts are securely concealed and protected against unauthorized access.

**Relevant Links:**
- [ENISA Configuration Security](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Implement robust system preamble protection.
- Regularly audit system configurations to ensure prompt security.

**Timeline for Mitigation:** High-priority, immediate implementation within 3-6 months.

**Use Case for Mitigation:** Securely encrypt and restrict access to system prompts to prevent leakage and manipulation.

**References:**
- [ENISA Configuration Security](https://www.enisa.europa.eu)

---

### [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

**Severity Rating:** Medium

**Description:** Vector and embedding weaknesses arise when attackers exploit vulnerabilities in embedding vectors to infer sensitive data relationships or manipulate model behaviours. Improper handling of embeddings can lead to unintended inferences or data breaches.

- **Real-World Example:** Vulnerabilities in embedding vectors exploited by attackers to infer sensitive data relationships or manipulate model behaviour.

- **Challenges and Lessons Learned:** Protecting vector embeddings is crucial, as they form the core of model inference. Lessons learned underscore the need for encryption and differential privacy.

- **ENISA Mapping:**
  - **ENISA Embedding Security:** Promotes secure handling of vectors and embeddings to prevent unauthorized inference.

**Relevant Links:**
- [ENISA Embedding Security](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Use encrypted embeddings and apply differential privacy to embeddings.

**Timeline for Mitigation:** Medium-priority, implementation within 6 months.

**Use Case for Mitigation:** Apply encryption to embedding vectors to enhance security against inference attacks.

**References:**
- [ENISA Embedding Security](https://www.enisa.europa.eu)

---

### [LLM09:2025 Misinformation](https://genai.owasp.org/)

**Severity Rating:** High

**Description:** Misinformation occurs when LLMs generate and propagate inaccurate or misleading information, leading to disinformation campaigns or incorrect conclusions by users. This vulnerability can undermine trust and cause significant harm if unverified information is treated as factual.

- **Real-World Example:** An LLM generates inaccurate information that is propagated as factual, leading to widespread disinformation.

- **Challenges and Lessons Learned:** Misinformation is particularly challenging given the scale and speed at which LLMs can generate and spread content. Lessons learned stress the importance of retrieval-augmented generation (RAG) and human oversight.

- **ENISA Mapping:**
  - **ENISA’s Disinformation Mitigation:** Recommends using retrieval-augmented generation (RAG), human oversight, and cross-verification.

**Relevant Links:**
- [ENISA Disinformation Mitigation](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Implement retrieval-augmented generation (RAG) to cross-reference generated content.
- Establish human oversight to verify LLM outputs before dissemination.

**Timeline for Mitigation:** High-priority, immediate implementation within 3-6 months.

**Use Case for Mitigation:** In content generation applications, ensure that information provided by the LLM is verified against trusted sources to mitigate misinformation risks.

**References:**
- [ENISA Disinformation Mitigation](https://www.enisa.europa.eu)

---

### [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

**Severity Rating:** Medium

**Description:** Unbounded consumption occurs when LLMs continue processing excessive amounts of data, leading to resource exhaustion or system crashes. This vulnerability is particularly prevalent in situations where no limits are placed on user inputs or outputs.

- **Real-World Example:** An LLM continuously processes recursive or unusually large user inputs, resulting in a system crash.

- **Challenges and Lessons Learned:** Controlling resource utilization is a significant challenge for LLMs, especially when dealing with large and unpredictable inputs. Lessons learned highlight the need for implementing resource thresholds.

- **ENISA Mapping:**
  - **ENISA Resource Management Recommendations:** Advises implementing limits on computational resources and monitoring usage.

**Relevant Links:**
- [ENISA Resource Management](https://www.enisa.europa.eu)

**Mitigation Strategies:**
- Set input and output limits for LLMs to control data consumption.
- Monitor and restrict computational resources used during LLM processing.

**Timeline for Mitigation:** Medium-priority, implementation within 6-9 months.

**Use Case for Mitigation:** In public-facing chatbot systems, set strict limits on input length and response size to avoid excessive resource consumption.

**References:**
- [ENISA Resource Management](https://www.enisa.europa.eu)

---

## Stakeholder Guidance

### For Developers
- Review ENISA's guidelines on secure software development: [ENISA Secure Development](https://www.enisa.europa.eu/publications/guideline-on-software-security)
- Implement secure coding practices specifically for LLMs, such as input validation and output sanitization, to mitigate injection attacks and sensitive data exposure.
- Use testing tools to identify vulnerabilities within LLM integration points.

### For Security Professionals
- Leverage ENISA's risk assessment framework for AI: [ENISA Risk Assessment](https://www.enisa.europa.eu/topics/risk-management)
- Conduct regular adversarial testing and penetration testing to identify vulnerabilities in LLMs.
- Implement threat modeling and supply chain risk management specifically for LLM environments.

### For Decision-Makers
- Refer to ENISA's recommendations on AI governance: [ENISA AI Governance](https://www.enisa.europa.eu/publications/ai-governance-framework)
- Develop policies that govern the deployment and use of LLMs, ensuring compliance with both security and privacy standards.
- Prioritize budget allocation for security testing, regular model updates, and mitigation strategies to ensure long-term LLM security.

---

## Incident Response Guidance

To ensure swift responses to LLM security incidents, consider the following:
- Develop an incident response plan specific to LLM vulnerabilities, focusing on prompt injection, sensitive information exposure, and data poisoning.
- Monitor LLM outputs and logs for unusual patterns that might indicate an attack or misuse.
- Train incident response teams on handling LLM-specific risks, including model retraining and data rollback.

---

## Glossary

- **LLM (Large Language Model):** A type of artificial intelligence model designed to understand and generate natural language.
- **Federated Learning:** A machine learning technique that trains an algorithm across multiple decentralized devices without exchanging data.
- **Differential Privacy:** A system that allows the extraction of useful information from datasets while protecting individual privacy.
- **Retrieval-Augmented Generation (RAG):** A technique that combines retrieval of external knowledge with generation capabilities to produce accurate outputs.
- **Adversarial Testing:** A method used to assess model robustness by simulating attacks to identify vulnerabilities.
- **Supply Chain Risk Management:** The process of identifying, assessing, and mitigating risks associated with third-party software or datasets used in LLMs.

---

The EU plays an important part in regulating and securing systems worldwide. Organizations that trade with the region must comply with the requirements to ensure ethical and secure, products, services and solutions. For more info visit [**ENISA**](https://www.enisa.europa.eu/) website

---

