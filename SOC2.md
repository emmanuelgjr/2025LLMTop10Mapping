# OWASP Top 10 for Large Language Model Applications 2025 Mapped to SOC 2

This repo provides a detailed mapping of the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to [**SOC 2 Trust Service Criteria (TSC)**](https://www.aicpa-cima.com/topic/audit-assurance/audit-and-assurance-greater-than-soc-2), specifically covering Security, Availability, Confidentiality, Processing Integrity, and Privacy. This mapping supports developers, risk managers, and security teams in aligning AI-specific security practices with SOC 2 standards to enhance trustworthy, safe, and compliant AI applications in various sectors.

Each vulnerability includes scenarios, impacts on stakeholders, ethical considerations, and guidance for implementing these practices within the AI lifecycle.

| **Vulnerability**                         | **Risk Level** | **SOC 2 Trust Service Criteria**                   | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|----------------|----------------------------------------------------|--------------------------------------------|---------------------------------------------------------|
| LLM01:2025 Prompt Injection               | High           | CC6.1, CC7.2, PI1.2                               | Unauthorized actions, data exposure       | Input validation, prompt integrity enforcement          |
| LLM02:2025 Sensitive Information Disclosure | High          | CC6.2, CC7.2, C1.2, P3.2                          | Disclosure of sensitive data              | Data masking, access controls                           |
| LLM03:2025 Supply Chain Vulnerabilities   | Medium         | CC1.4, CC9.2, PI1.3                               | Compromised dependencies                   | Dependency monitoring, supply chain risk assessment     |
| LLM04:2025 Data and Model Poisoning       | High           | PI1.2, CC7.2, CC8.1                               | Compromised data integrity, model biases   | Data integrity checks, secure data handling             |
| LLM05:2025 Insecure Output Handling       | Medium         | CC6.1, CC6.7, PI1.2                               | Unauthorized output actions                | Output filtering, standardized format requirements      |
| LLM06:2025 Excessive Agency               | Medium         | CC6.3, PI1.3                                      | Unintended autonomous actions             | Least privilege, human approval for high-risk actions   |
| LLM07:2025 System Prompt Leakage          | Medium         | CC6.1, CC7.2, C1.2                                | Unauthorized prompt exposure               | Secure prompt storage, access restrictions              |
| LLM08:2025 Vector and Embedding Weaknesses | Medium         | CC6.7, PI1.2, C1.2                                | Biased or malicious outputs                | Bias testing, secure vector storage                     |
| LLM09:2025 Misinformation                 | Medium         | PI1.2, CC7.2                                      | Inaccurate or misleading content          | Cross-verification, human oversight                     |
| LLM10:2025 Unbounded Consumption          | Low            | CC6.1, CC8.1, A1.2                                | Resource exhaustion, degraded performance  | Rate-limiting, load balancing                           |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Attackers manipulate prompt inputs to change model behaviour, potentially enabling unauthorized actions, disclosing sensitive information, or bypassing security controls.

- **Example Scenario**: A customer support chatbot is manipulated by a prompt injection attack, causing it to reveal sensitive information about other customers.

- **Stakeholder Impact**:
  - **Developers**: Implement prompt validation to prevent manipulative inputs.
  - **Risk Managers**: Address risks associated with unauthorized access through prompt injection.
  - **Compliance Officers**: Ensure compliance with access control policies and avoid data exposure.

- **Ethical Considerations**: Ensuring secure prompt handling protects user data privacy and prevents unauthorized manipulation.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.1**: Implement strong access controls to secure prompts.
  - **CC7.2**: Regularly monitor prompts to detect potential injection.
  - **PI1.2**: Ensure accurate processing through validated prompt handling.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Use strict input validation frameworks and regular expression filters.
    - Define acceptable input formats to restrict prompt structure.
  - **Detective Controls**:
    - Continuously monitor prompt inputs for anomalies.
  - **Corrective Actions**:
    - Quarantine suspicious prompt inputs and monitor for further signs of injection attempts.

- **Recommended Tools**: OWASP ZAP, regex-based validators, boundary-check tools.

- **Key Risks**: Unauthorized access, data leakage, prompt manipulation.

- **Top Mitigation Steps**: Input validation, prompt integrity enforcement, continuous monitoring.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Sensitive information disclosure occurs when an LLM unintentionally reveals private data, including PII or proprietary content, due to weak access controls or insufficient filtering mechanisms.

- **Example Scenario**: A healthcare chatbot inadvertently reveals a patient’s medical information due to improper data masking.

- **Stakeholder Impact**:
  - **Developers**: Responsible for implementing data masking and access controls.
  - **Risk Managers**: Protect sensitive information to mitigate legal and reputational risks.
  - **Compliance Officers**: Ensure compliance with privacy regulations, such as GDPR.

- **Ethical Considerations**: Protecting sensitive information upholds user privacy and trust in the system.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.2**: Implement access controls to prevent unauthorized data disclosure.
  - **CC7.2**: Ensure output filtering for secure information disclosure.
  - **P3.2**: Apply privacy controls to protect user data.
  - **C1.2**: Secure confidentiality by enforcing strict access controls.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce data masking on all sensitive outputs.
    - Implement differential privacy to protect individual data points.
  - **Detective Controls**:
    - Regularly audit model outputs for potential privacy breaches.
  - **Corrective Actions**:
    - Automatically redact or mask sensitive information found in outputs.

- **Recommended Tools**: TensorFlow Privacy, differential privacy frameworks.

- **Key Risks**: Unauthorized access to sensitive data, legal non-compliance.

- **Top Mitigation Steps**: Data masking, access controls, audit trails.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Supply chain vulnerabilities stem from third-party dependencies that, if unvetted, may introduce malicious elements or unaddressed vulnerabilities into the system.

- **Example Scenario**: A third-party dependency used in the LLM’s library introduces a vulnerability that allows remote code execution.

- **Stakeholder Impact**:
  - **Developers**: Must vet and verify the security of each component.
  - **Risk Managers**: Manage third-party risks and ensure secure supply chains.
  - **Compliance Officers**: Enforce third-party security requirements.

- **Ethical Considerations**: Maintaining secure supply chains supports transparency and user trust.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC1.4**: Monitor supply chain risk and verify third-party reliability.
  - **CC9.2**: Enforce vendor management policies.
  - **PI1.3**: Maintain integrity in processing to ensure secure component use.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce strict third-party software audits and use trusted vendors.
    - Require security attestations for all third-party software.
  - **Detective Controls**:
    - Conduct regular vulnerability scans on dependencies.
  - **Corrective Actions**:
    - Remove or patch compromised dependencies immediately.

- **Recommended Tools**: OWASP Dependency-Check, Snyk, Veracode.

- **Key Risks**: Malicious components, unverified dependencies.

- **Top Mitigation Steps**: Regular audits, dependency monitoring tools, supply chain security policies.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data and model poisoning occurs when malicious data is injected into training datasets, skewing model predictions or introducing biases.

- **Example Scenario**: Poisoned data in a financial model causes biased predictions, leading to incorrect financial advice.

- **Stakeholder Impact**:
  - **Developers**: Implement data validation and secure ingestion pipelines.
  - **Risk Managers**: Monitor data sources to prevent integrity breaches.
  - **Compliance Officers**: Ensure data integrity to avoid biases.

- **Ethical Considerations**: Ensuring data integrity supports fairness and prevents harmful consequences.

- **SOC 2 Trust Service Criteria Mapping**:
  - **PI1.2**: Ensure processing accuracy and prevent compromised data.
  - **CC7.2**: Monitor data handling to maintain security.
  - **CC8.1**: Protect data against tampering or poisoning.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply robust data validation checks and provenance controls.
  - **Detective Controls**:
    - Implement anomaly detection on input data for potential poisoning.
  - **Corrective Actions**:
    - Retrain models if significant poisoning is detected.

- **Recommended Tools**: Anomaly detection tools, data provenance solutions.

- **Key Risks**: Compromised data integrity, biased outputs.

- **Top Mitigation Steps**: Data audits, secure data pipelines, anomaly detection.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: Insecure output handling may result in unfiltered LLM outputs that disclose sensitive information or perform unintended actions (e.g., HTML injection). Outputs must be securely filtered and validated.

- **Example Scenario**: A financial chatbot discloses sensitive data due to improper output handling.

- **Stakeholder Impact**:
  - **Developers**: Implement secure output handling and formatting.
  - **Risk Managers**: Mitigate data leakage risks.
  - **Compliance Officers**: Ensure outputs meet security and privacy regulations.

- **Ethical Considerations**: Preventing unauthorized disclosures upholds privacy and user trust.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.1**: Define and enforce access control for outputs.
  - **CC6.7**: Implement strong data filtering and validation.
  - **PI1.2**: Regularly monitor output handling.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Use output encoding and escaping to prevent injection attacks.
    - Standardize output formatting.
  - **Detective Controls**:
    - Regularly review output handling policies and validate against expected formats.
  - **Corrective Actions**:
    - Automatically redact or modify inappropriate outputs.

- **Recommended Tools**: OWASP Output Encoding Libraries, Secure Formatting Libraries, Data Redaction Tools.

- **Key Risks**: Data leakage, injection vulnerabilities.

- **Top Mitigation Steps**: Output filtering, secure formatting, continuous audits.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to unintended autonomous actions taken by an LLM, which could lead to harmful or unauthorized decisions.

- **Example Scenario**: An AI assistant autonomously processes high-value transactions without human approval, posing financial risks.

- **Stakeholder Impact**:
  - **Developers**: Implement role-based access controls to limit LLM actions.
  - **Risk Managers**: Limit the LLM’s autonomy for high-risk actions.
  - **Compliance Officers**: Ensure actions adhere to company policies and legal standards.

- **Ethical Considerations**: Limiting model autonomy prevents unintended harm and supports accountability.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.3**: Enforce least privilege and restrict LLM permissions.
  - **PI1.3**: Define human approval for high-stakes decisions.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce least privilege and limit permissions.
    - Use human-in-the-loop (HITL) protocols for high-impact actions.
  - **Detective Controls**:
    - Continuously monitor LLM logs to identify unauthorized actions.
  - **Corrective Actions**:
    - Review incidents to refine role-based access control policies.

- **Recommended Tools**: Role-Based Access Control (RBAC) systems, HITL workflow tools.

- **Key Risks**: Unauthorized decisions, safety risks.

- **Top Mitigation Steps**: Enforce least privilege, HITL approval, access controls.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompt leakage occurs when internal prompts that guide the model’s responses are exposed, allowing attackers to manipulate or bypass controls.

- **Example Scenario**: Attackers access system prompts, allowing them to bypass security settings.

- **Stakeholder Impact**:
  - **Developers**: Secure prompt data with strong access controls.
  - **Risk Managers**: Protect against prompt exposure to maintain operational security.
  - **Compliance Officers**: Enforce confidentiality and integrity of system prompts.

- **Ethical Considerations**: Protecting system prompts prevents unauthorized manipulations.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.1**: Protect prompt storage and enforce strict access controls.
  - **CC7.2**: Regularly monitor and review prompt configurations.
  - **C1.2**: Safeguard confidentiality for prompt data.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encrypt and restrict prompt access.
  - **Detective Controls**:
    - Implement prompt access logging and monitoring.
  - **Corrective Actions**:
    - Update or revoke exposed prompt data.

- **Recommended Tools**: Access Management Solutions, Encryption Libraries.

- **Key Risks**: Unauthorized prompt access, model manipulation.

- **Top Mitigation Steps**: Secure prompt storage, access control, policy compliance checks.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Weak embeddings can lead to biased or adversarially manipulated outputs, impacting model reliability and fairness.

- **Example Scenario**: Bias in embeddings causes a job-matching LLM to recommend certain demographics unfairly.

- **Stakeholder Impact**:
  - **Developers**: Use bias detection and secure embedding management.
  - **Risk Managers**: Ensure unbiased outputs and minimize reputational risks.
  - **Compliance Officers**: Validate outputs for fairness.

- **Ethical Considerations**: Ensuring fairness in embeddings promotes equitable outcomes.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.7**: Enforce robust data handling for embeddings.
  - **PI1.2**: Monitor for biases and adversarial weaknesses.
  - **C1.2**: Protect embedding confidentiality.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Conduct bias and adversarial testing.
  - **Detective Controls**:
    - Regularly review embeddings for unusual patterns.
  - **Corrective Actions**:
    - Retrain embeddings if biases are detected.

- **Recommended Tools**: Fairlearn, Microsoft InterpretML.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation occurs when an LLM generates incorrect or misleading information.

- **Example Scenario**: A healthcare chatbot provides incorrect medical advice.

- **Stakeholder Impact**:
  - **Developers**: Implement verification for high-stakes outputs.
  - **Risk Managers**: Ensure accurate outputs to avoid misinformation risks.
  - **Compliance Officers**: Meet accuracy standards in outputs.

- **Ethical Considerations**: Accurate information delivery is essential to maintain trust.

- **SOC 2 Trust Service Criteria Mapping**:
  - **PI1.2**: Regularly monitor output quality.
  - **CC7.2**: Validate accuracy in data processing.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Cross-verify high-risk outputs.
  - **Detective Controls**:
    - Set up real-time validation for outputs.
  - **Corrective Actions**:
    - Correct misinformation promptly.

- **Recommended Tools**: Verification platforms, cross-validation systems.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Excessive resource usage by LLMs can lead to denial of service (DoS) and degraded performance.

- **Example Scenario**: High usage exhausts resources, causing service downtime.

- **Stakeholder Impact**:
  - **Developers**: Enforce resource limits.
  - **Risk Managers**: Prevent DoS and maintain performance.
  - **Compliance Officers**: Ensure SLA compliance.

- **Ethical Considerations**: Efficient resource management ensures continuous service.

- **SOC 2 Trust Service Criteria Mapping**:
  - **CC6.1**: Define resource control policies.
  - **CC8.1**: Continuously monitor system resource usage.
  - **A1.2**: Implement rate limits.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply rate-limiting and load balancing.
  - **Detective Controls**:
    - Monitor resource usage spikes.
  - **Corrective Actions**:
    - Adjust limits as needed during peak usage.

- **Recommended Tools**: Rate Limiting Tools (e.g., Kong), Load Balancing Solutions, Resource Monitors (e.g., Prometheus).

---


This repository provides a comprehensive mapping of the OWASP Top 10 for LLM Applications 2025 to SOC 2 Trust Service Criteria, offering essential guidance for implementing secure, reliable, and trustworthy AI applications. By aligning AI-specific vulnerabilities with SOC 2 standards, this guide helps developers, risk managers, and compliance officers integrate robust security measures across the AI lifecycle.

The integration of SOC 2 principles across vulnerabilities—such as prompt injection, sensitive information disclosure, and unbounded consumption—supports a proactive and structured approach to AI security and governance. From enforcing input validation to implementing human-in-the-loop controls for high-stakes decisions, each strategy enhances the integrity, privacy, and availability of AI systems in diverse applications, from customer support to critical infrastructure.

SOC 2 compliance not only fulfills regulatory expectations but also strengthens user trust and safeguards organizational assets against emerging risks in AI. As AI technology continues to evolve, maintaining SOC 2 alignment will be crucial for managing risk, ensuring compliance, and fostering ethical practices in artificial intelligence.

### Next Steps:
1. **Continuous Monitoring**: Implement automated monitoring and alerting mechanisms to track compliance and respond to vulnerabilities in real-time.
2. **Periodic Audits**: Regularly review and audit AI applications to maintain alignment with SOC 2 standards as requirements and AI models evolve.
3. **Engagement with AI and Security Communities**: Collaborate with industry peers, compliance experts, and AI researchers to stay updated on best practices and evolving security threats.

Embedding SOC 2 principles into the AI development process, allows organizations to achieve a balance between innovation and responsibility, creating AI solutions that are secure, resilient, and aligned with ethical and regulatory standards.

---

For more resources on SOC 2 compliance and AI security best practices, explore the following:
- [SOC 2 Overview by AICPA](https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpasoc2report.html)
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org)

