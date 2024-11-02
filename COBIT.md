# OWASP Top 10 for Large Language Model Applications 2025 Mapped to COBIT

This repo provides an extensive mapping of the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to [**COBIT**](https://www.isaca.org/resources/cobit) principles, covering **Evaluate, Direct, and Monitor (EDM)**, **Align, Plan, and Organize (APO)**, **Build, Acquire, and Implement (BAI)**, and **Deliver, Service, and Support (DSS)**. This mapping aids governance, security teams, and developers in aligning AI-specific vulnerabilities within an enterprise governance framework to ensure secure, compliant, and efficient AI deployments.

Each vulnerability includes real-world scenarios, stakeholder impacts, ethical considerations, mitigation strategies, and guidance for implementing these practices within the AI lifecycle.

| **Vulnerability**                         | **Risk Level** | **COBIT Domains**                                   | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|----------------|----------------------------------------------------|--------------------------------------------|---------------------------------------------------------|
| LLM01:2025 Prompt Injection               | High           | APO12, BAI06, DSS05                                | Unauthorized actions, data exposure       | Input validation, prompt integrity enforcement          |
| LLM02:2025 Sensitive Information Disclosure | High          | APO13, DSS06, EDM03                                | Disclosure of sensitive data              | Data masking, access controls                           |
| LLM03:2025 Supply Chain Vulnerabilities   | Medium         | BAI09, APO10, DSS03                                | Compromised dependencies                   | Dependency monitoring, supply chain risk assessment     |
| LLM04:2025 Data and Model Poisoning       | High           | APO12, BAI02, DSS06                                | Compromised data integrity, model biases   | Data integrity checks, secure data handling             |
| LLM05:2025 Insecure Output Handling       | Medium         | BAI06, DSS05, EDM03                                | Unauthorized output actions                | Output filtering, standardized format requirements      |
| LLM06:2025 Excessive Agency               | Medium         | APO01, BAI10, DSS06                                | Unintended autonomous actions             | Least privilege, human approval for high-risk actions   |
| LLM07:2025 System Prompt Leakage          | Medium         | APO13, DSS05, EDM03                                | Unauthorized prompt exposure               | Secure prompt storage, access restrictions              |
| LLM08:2025 Vector and Embedding Weaknesses | Medium         | APO12, DSS06, EDM03                                | Biased or malicious outputs                | Bias testing, secure vector storage                     |
| LLM09:2025 Misinformation                 | Medium         | APO12, BAI02, DSS05                                | Inaccurate or misleading content          | Cross-verification, human oversight                     |
| LLM10:2025 Unbounded Consumption          | Low            | DSS03, APO11, BAI09                                | Resource exhaustion, degraded performance  | Rate-limiting, load balancing                           |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Attackers manipulate prompt inputs to alter model behavior, potentially enabling unauthorized actions, disclosing sensitive information, or bypassing security controls.

- **Example Scenario**: A customer support chatbot is manipulated by a prompt injection attack, causing it to reveal sensitive information about other customers.

- **Stakeholder Impact**:
  - **Developers**: Must implement robust prompt validation to prevent manipulative inputs.
  - **Risk Managers**: Address risks associated with unauthorized access through prompt injection.
  - **Governance Teams**: Monitor compliance with data security policies to prevent prompt manipulation.

- **Ethical Considerations**: Ensuring secure prompt handling protects sensitive data and supports user trust.

- **COBIT Domain Mapping**:
  - **APO12 (Manage Risk)**: Establish policies to prevent unauthorized prompt access.
  - **BAI06 (Manage Changes)**: Implement changes in input validation to handle prompt security.
  - **DSS05 (Manage Security Services)**: Monitor and protect prompts as part of ongoing security services.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce input validation rules and limit acceptable prompt formats.
    - Define access rules and boundaries for prompt-based interactions.
  - **Detective Controls**:
    - Monitor prompts for signs of injection and establish logs for anomaly detection.
  - **Corrective Actions**:
    - Quarantine suspicious prompts and regularly update security policies.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define acceptable prompt structures aligned with business rules.
  - **Deployment Stage**: Continuously monitor prompt inputs for suspicious activity.

- **Recommended Tools**: OWASP ZAP, regex validators, and boundary-check tools.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Sensitive information disclosure occurs when an LLM unintentionally reveals private data, including PII or proprietary content, due to weak access controls or insufficient filtering mechanisms.

- **Example Scenario**: A healthcare chatbot inadvertently reveals a patient’s medical information due to inadequate data masking and access restrictions.

- **Stakeholder Impact**:
  - **Developers**: Implement data masking and secure output handling.
  - **Risk Managers**: Protect sensitive information to comply with privacy laws and prevent data breaches.
  - **Governance Teams**: Establish monitoring controls to detect unauthorized access.

- **Ethical Considerations**: Preventing unauthorized data disclosures upholds user privacy and trust.

- **COBIT Domain Mapping**:
  - **APO13 (Manage Security)**: Establish and enforce security and data protection measures.
  - **DSS06 (Manage Business Process Controls)**: Monitor and ensure compliance with data security policies.
  - **EDM03 (Ensure Risk Optimization)**: Align data handling practices with enterprise risk policies.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Mask all sensitive outputs and implement differential privacy techniques.
  - **Detective Controls**:
    - Audit outputs periodically for adherence to privacy policies.
  - **Corrective Actions**:
    - Automatically redact or mask sensitive information in outputs.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Apply data anonymization and privacy protocols.
  - **Deployment Stage**: Implement continuous monitoring for data handling compliance.

- **Recommended Tools**: TensorFlow Privacy, data masking tools, differential privacy frameworks.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Supply chain vulnerabilities introduced via unvetted third-party dependencies can affect the security of LLM applications, potentially enabling unauthorized access or data manipulation.

- **Example Scenario**: A compromised library used within an LLM application introduces a vulnerability that allows for remote code execution.

- **Stakeholder Impact**:
  - **Developers**: Vet and verify the security of third-party dependencies.
  - **Risk Managers**: Continuously assess risks related to third-party software.
  - **Governance Teams**: Establish vendor risk management and continuous auditing practices.

- **Ethical Considerations**: Ensuring secure third-party dependencies builds user trust and system integrity.

- **COBIT Domain Mapping**:
  - **BAI09 (Manage Assets)**: Enforce secure integration with external dependencies.
  - **APO10 (Manage Vendors)**: Implement vendor risk management to monitor supply chain risks.
  - **DSS03 (Manage Problems)**: Continuously address issues and vulnerabilities in third-party components.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Require attestations and enforce software audits for third-party components.
  - **Detective Controls**:
    - Scan dependencies for vulnerabilities as part of regular assessments.
  - **Corrective Actions**:
    - Isolate or patch compromised dependencies as soon as vulnerabilities are detected.

- **Implementation Notes by AI Lifecycle**:
  - **Development Stage**: Monitor dependencies continuously.
  - **Deployment Stage**: Audit third-party integrations regularly.

- **Recommended Tools**: OWASP Dependency-Check, Snyk, Veracode.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data poisoning attacks inject malicious data into datasets, skewing model predictions or introducing biases that can compromise model integrity and output reliability.

- **Example Scenario**: Poisoned data in a financial model causes biased predictions, potentially affecting decisions.

- **Stakeholder Impact**:
  - **Developers**: Implement secure data validation and handling.
  - **Risk Managers**: Assess risks associated with compromised data integrity.
  - **Governance Teams**: Monitor compliance with data quality standards to ensure fair outputs.

- **Ethical Considerations**: Ensuring data integrity supports fair outcomes and mitigates harmful biases.

- **COBIT Domain Mapping**:
  - **APO12 (Manage Risk)**: Evaluate and control risks associated with data integrity.
  - **BAI02 (Manage Requirements)**: Define requirements to ensure data quality and prevent poisoning.
  - **DSS06 (Manage Business Process Controls)**: Enforce ongoing validation and monitoring for data quality.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Implement data validation controls and secure ingestion practices.
  - **Detective Controls**:
    - Use anomaly detection to monitor training data for potential poisoning.
  - **Corrective Actions**:
    - Retrain models if significant data poisoning is detected.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Apply rigorous data integrity checks.
  - **Monitoring Stage**: Continuously review data for poisoning attempts.

- **Recommended Tools**: Data provenance solutions, anomaly detection systems.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: Insecure output handling may lead to unfiltered LLM outputs disclosing sensitive information or executing unintended actions, such as unauthorized data exposure or injection vulnerabilities.

- **Example Scenario**: A customer service LLM discloses sensitive customer data due to inadequate output filtering.

- **Stakeholder Impact**:
  - **Developers**: Implement secure output handling and filtering.
  - **Risk Managers**: Ensure data leakage risks are mitigated in all outputs.
  - **Compliance Teams**: Enforce data handling policies for compliance with privacy standards.

- **Ethical Considerations**: Preventing unauthorized disclosures upholds privacy, user trust, and compliance.

- **COBIT Domain Mapping**:
  - **BAI06 (Manage Changes)**: Implement output handling changes that prioritize security.
  - **DSS05 (Manage Security Services)**: Ensure secure output handling is part of ongoing security services.
  - **EDM03 (Ensure Risk Optimization)**: Align output management practices with enterprise risk policies.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encode and filter outputs to prevent data leaks and injection attacks.
  - **Detective Controls**:
    - Periodically audit output handling for compliance with security standards.
  - **Corrective Actions**:
    - Flag and mask sensitive output data as required.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Enforce secure output handling protocols.
  - **Post-Deployment**: Continuously monitor outputs for security risks.

- **Recommended Tools**: Output encoding libraries, secure formatting libraries, data redaction tools.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to unintended autonomous actions by an LLM, potentially leading to risky or unauthorized decisions, especially in high-stakes applications.

- **Example Scenario**: An LLM autonomously authorizes high-value transactions without requiring human approval, leading to potential financial risks.

- **Stakeholder Impact**:
  - **Developers**: Limit LLM permissions and implement access controls.
  - **Risk Managers**: Ensure critical decisions require human oversight.
  - **Governance Teams**: Monitor compliance with role-based access and control policies.

- **Ethical Considerations**: Limiting LLM autonomy promotes accountability and minimizes risks.

- **COBIT Domain Mapping**:
  - **APO01 (Manage the IT Management Framework)**: Define boundaries for acceptable actions by AI.
  - **BAI10 (Manage Configuration)**: Ensure LLM autonomy is limited through configuration management.
  - **DSS06 (Manage Business Process Controls)**: Implement controls for high-stakes actions to require human approval.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply least privilege for LLM permissions and enforce human-in-the-loop (HITL) for critical decisions.
  - **Detective Controls**:
    - Set alerts for high-stakes or unauthorized autonomous actions.
  - **Corrective Actions**:
    - Review incidents and adjust access policies.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define model autonomy limits.
  - **Deployment Stage**: Monitor high-stakes decisions for compliance.

- **Recommended Tools**: RBAC systems, HITL workflow systems, alerting tools.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompt leakage occurs when internal prompts that guide the model’s responses are exposed, allowing attackers to manipulate or bypass security controls.

- **Example Scenario**: An attacker accesses system prompts, manipulating responses to reveal sensitive information or bypass restrictions.

- **Stakeholder Impact**:
  - **Developers**: Secure prompt data storage and restrict access.
  - **Risk Managers**: Protect prompt access to prevent unauthorized use.
  - **Compliance Teams**: Ensure prompt management complies with confidentiality standards.

- **Ethical Considerations**: Protecting prompts supports reliable, secure interactions and prevents unauthorized manipulation.

- **COBIT Domain Mapping**:
  - **APO13 (Manage Security)**: Protect and monitor prompt data.
  - **DSS05 (Manage Security Services)**: Enforce secure prompt storage.
  - **EDM03 (Ensure Risk Optimization)**: Ensure prompt handling aligns with risk policies.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encrypt prompt data and limit access to authorized personnel only.
  - **Detective Controls**:
    - Log prompt access and implement monitoring.
  - **Corrective Actions**:
    - Update and restrict prompts if unauthorized access is detected.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Ensure prompt storage is encrypted and access-controlled.
  - **Post-Deployment**: Continuously monitor and log prompt access.

- **Recommended Tools**: Secure configuration management tools, access management solutions, encryption libraries.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Weaknesses in data embeddings and vectors can lead to biased or adversarially manipulated outputs, impacting model reliability and fairness.

- **Example Scenario**: Biased embeddings in a job-matching LLM result in unfair recommendations, potentially causing reputational damage and regulatory issues.

- **Stakeholder Impact**:
  - **Developers**: Ensure embeddings are managed securely and monitor for biases.
  - **Risk Managers**: Regularly review embeddings for adversarial manipulation.

- **Ethical Considerations**: Ensuring fairness in embeddings supports equitable outcomes and aligns with ethical AI practices.

- **COBIT Domain Mapping**:
  - **APO12 (Manage Risk)**: Regularly evaluate embedding risks.
  - **DSS06 (Manage Business Process Controls)**: Implement quality checks for bias and integrity.
  - **EDM03 (Ensure Risk Optimization)**: Align embedding management with organizational risk standards.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Conduct bias testing on embeddings to ensure fairness.
  - **Detective Controls**:
    - Monitor embeddings for signs of manipulation or bias.
  - **Corrective Actions**:
    - Retrain embeddings if integrity issues are identified.

- **Implementation Notes by AI Lifecycle**:
  - **Training Stage**: Conduct bias checks on embeddings.
  - **Post-Deployment**: Regularly assess embedding fairness.

- **Recommended Tools**: Fairlearn, Microsoft InterpretML.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation occurs when an LLM generates inaccurate or misleading information, particularly impactful in high-stakes applications like healthcare or finance.

- **Example Scenario**: A healthcare chatbot provides incorrect medical advice, potentially endangering users.

- **Stakeholder Impact**:
  - **Developers**: Implement verification for high-stakes outputs.
  - **Risk Managers**: Ensure accurate information through oversight.

- **Ethical Considerations**: Accurate information delivery is essential for trust and safety.

- **COBIT Domain Mapping**:
  - **APO12 (Manage Risk)**: Address risks associated with misinformation.
  - **BAI02 (Manage Requirements)**: Define requirements for accurate outputs.
  - **DSS05 (Manage Security Services)**: Establish information verification processes.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Implement cross-verification with reliable sources.
  - **Detective Controls**:
    - Set up real-time validation of outputs.
  - **Corrective Actions**:
    - Adjust models when misinformation is identified.

- **Recommended Tools**: Verification platforms, cross-validation systems.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Excessive resource consumption by LLMs can lead to degraded performance or denial of service, impacting system availability.

- **Example Scenario**: An LLM monopolizes resources, causing slowdowns and impacting other services.

- **Stakeholder Impact**:
  - **Developers**: Implement rate limits to manage resource usage.
  - **Risk Managers**: Ensure system availability and prevent resource exhaustion.

- **Ethical Considerations**: Efficient resource management promotes continuous, reliable service.

- **COBIT Domain Mapping**:
  - **DSS03 (Manage Problems)**: Identify and resolve resource consumption issues.
  - **APO11 (Manage Quality)**: Establish and monitor quality controls for resource use.
  - **BAI09 (Manage Assets)**: Ensure resource management policies are in place.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply rate-limiting and load balancing for resource management.
  - **Detective Controls**:
    - Monitor resource usage patterns for anomalies.
  - **Corrective Actions**:
    - Adjust usage limits dynamically during peak demand.

- **Recommended Tools**: Rate-limiting solutions (e.g., Kong), load balancers, resource monitors (e.g., Prometheus).

---

This mapping of the OWASP Top 10 for LLM Applications 2025 to COBIT demonstrates how AI-specific security vulnerabilities can be managed within an enterprise governance framework. COBIT principles integrated across domains such as **Risk Management**, **Asset Management**, and **Security Services**, organizations can build secure, reliable, and compliant AI systems that align with enterprise goals and regulatory requirements.

**Next Steps**:
1. **Regular Audits**: Perform routine audits to ensure compliance with COBIT-aligned controls.
2. **Cross-Functional Collaboration**: Facilitate collaboration between IT, risk management, and governance teams for cohesive security.
3. **Continuous Monitoring**: Implement real-time monitoring to detect and address vulnerabilities as they arise.

This alignment strengthens AI applications and builds a foundation of trust, accountability, and compliance in AI initiatives across the enterprise.
