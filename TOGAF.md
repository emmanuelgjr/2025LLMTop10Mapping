# OWASP Top 10 for Large Language Model Applications 2025 Mapped to TOGAF

This repo provides an in-depth mapping of the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to [**The Open Group Architecture Framework (TOGAF)**](https://pubs.opengroup.org/architecture/togaf8-doc/arch/) domains, specifically covering **Business Architecture, Data Architecture, Application Architecture,** and **Technology Architecture**. This mapping aids enterprise architects, developers, and risk managers in aligning AI-specific vulnerabilities with TOGAF’s enterprise architecture framework, ensuring secure, scalable, and compliant AI deployments within organizations.

Each vulnerability includes practical scenarios, stakeholder impacts, ethical considerations, mitigation strategies, and guidance for incorporating these practices within the AI lifecycle.

| **Vulnerability**                         | **Risk Level** | **TOGAF Domains**                                  | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|----------------|----------------------------------------------------|--------------------------------------------|---------------------------------------------------------|
| LLM01:2025 Prompt Injection               | High           | Business, Data, Application                        | Unauthorized actions, data exposure       | Input validation, prompt integrity enforcement          |
| LLM02:2025 Sensitive Information Disclosure | High          | Data, Technology                                   | Disclosure of sensitive data              | Data masking, access controls                           |
| LLM03:2025 Supply Chain Vulnerabilities   | Medium         | Technology, Application                            | Compromised dependencies                   | Dependency monitoring, supply chain risk assessment     |
| LLM04:2025 Data and Model Poisoning       | High           | Data, Technology                                   | Compromised data integrity, model biases   | Data integrity checks, secure data handling             |
| LLM05:2025 Insecure Output Handling       | Medium         | Data, Application                                  | Unauthorized output actions                | Output filtering, standardized format requirements      |
| LLM06:2025 Excessive Agency               | Medium         | Business, Application                              | Unintended autonomous actions             | Least privilege, human approval for high-risk actions   |
| LLM07:2025 System Prompt Leakage          | Medium         | Data, Technology                                   | Unauthorized prompt exposure               | Secure prompt storage, access restrictions              |
| LLM08:2025 Vector and Embedding Weaknesses | Medium         | Data, Application                                  | Biased or malicious outputs                | Bias testing, secure vector storage                     |
| LLM09:2025 Misinformation                 | Medium         | Business, Data, Application                        | Inaccurate or misleading content          | Cross-verification, human oversight                     |
| LLM10:2025 Unbounded Consumption          | Low            | Technology, Application                            | Resource exhaustion, degraded performance  | Rate-limiting, load balancing                           |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Attackers manipulate prompt inputs to alter model behavior, potentially enabling unauthorized actions, disclosing sensitive information, or bypassing security controls.

- **Example Scenario**: A customer support chatbot is manipulated by a prompt injection attack, causing it to reveal sensitive information about other customers.

- **Stakeholder Impact**:
  - **Developers**: Must implement robust prompt validation to prevent manipulative inputs.
  - **Architects**: Ensure the application architecture is resilient to prompt-based vulnerabilities.
  - **Risk Managers**: Address risks associated with unauthorized access through prompt injection.

- **Ethical Considerations**: Ensuring secure prompt handling prevents unauthorized data exposure, supporting user trust and data privacy.

- **TOGAF Domain Mapping**:
  - **Business Architecture**: Define business rules around data access to protect sensitive customer information.
  - **Data Architecture**: Establish secure data flows and validate data integrity to prevent unauthorized access.
  - **Application Architecture**: Implement prompt validation mechanisms in applications to enforce secure input handling.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce strict input validation with clear constraints on acceptable prompt formats.
    - Define prompt policies at the business level to govern secure access and data integrity.
  - **Detective Controls**:
    - Monitor prompt usage patterns to detect and flag unusual or potentially malicious inputs.
  - **Corrective Actions**:
    - Quarantine suspicious inputs, implement prompt revalidation, and regularly update prompt security policies.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define prompt structures and validation requirements aligned with business rules.
  - **Deployment Stage**: Continuously monitor prompts for anomalies and potential risks.

- **Recommended Tools**: OWASP ZAP, regular expression validators, and boundary-check tools.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Sensitive information disclosure occurs when an LLM unintentionally reveals private data, such as PII or proprietary content, due to weak access controls or insufficient filtering mechanisms.

- **Example Scenario**: A healthcare chatbot inadvertently reveals a patient’s medical information due to inadequate data masking and access restrictions.

- **Stakeholder Impact**:
  - **Developers**: Responsible for implementing data masking and secure output handling.
  - **Architects**: Ensure data architecture prioritizes data confidentiality and access controls.
  - **Compliance Officers**: Maintain compliance with privacy regulations to protect sensitive information.

- **Ethical Considerations**: Protecting sensitive data prevents unauthorized disclosures, supporting compliance and user trust.

- **TOGAF Domain Mapping**:
  - **Data Architecture**: Enforce data masking and secure storage practices to safeguard sensitive information.
  - **Technology Architecture**: Implement encryption and access controls to prevent unauthorized data access.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply data masking on all sensitive outputs and ensure differential privacy for data handling.
  - **Detective Controls**:
    - Conduct periodic audits of model outputs for privacy compliance and potential information leaks.
  - **Corrective Actions**:
    - Automatically redact or mask sensitive information detected in outputs, and regularly update masking policies.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Apply data anonymization and storage restrictions.
  - **Deployment Stage**: Implement continuous monitoring for data handling compliance.

- **Recommended Tools**: TensorFlow Privacy, data masking tools, and differential privacy frameworks.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Vulnerabilities introduced via third-party dependencies can affect the security of LLM applications, potentially enabling unauthorized access or data manipulation.

- **Example Scenario**: A compromised library used within an LLM application introduces a vulnerability that allows for remote code execution, exposing the application to unauthorized manipulation.

- **Stakeholder Impact**:
  - **Developers**: Must vet and verify the security of all third-party components.
  - **Architects**: Ensure that the technology and application architectures integrate secure and vetted dependencies.
  - **Risk Managers**: Assess risks associated with third-party software and enforce secure vendor management practices.

- **Ethical Considerations**: Ensuring third-party components are secure and reliable helps maintain user trust and system integrity.

- **TOGAF Domain Mapping**:
  - **Technology Architecture**: Define policies for third-party software use, ensuring secure integration.
  - **Application Architecture**: Implement controls and dependency management for external software components.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Require security attestations from third-party vendors and enforce regular software audits.
  - **Detective Controls**:
    - Conduct vulnerability scans on dependencies as part of ongoing risk assessment.
  - **Corrective Actions**:
    - Isolate or patch compromised dependencies as soon as vulnerabilities are identified.

- **Implementation Notes by AI Lifecycle**:
  - **Development Stage**: Monitor dependencies and ensure they meet security requirements.
  - **Deployment Stage**: Regularly audit and validate all third-party integrations for compliance.

- **Recommended Tools**: OWASP Dependency-Check, Snyk, Veracode for software composition analysis.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data poisoning attacks inject malicious data into training datasets, skewing model predictions or introducing biases that can compromise model integrity and output reliability.

- **Example Scenario**: Poisoned data in a predictive model causes skewed outputs, leading to unreliable financial advice or biased predictions.

- **Stakeholder Impact**:
  - **Developers**: Implement data validation and secure ingestion pipelines.
  - **Risk Managers**: Continuously monitor for data integrity risks in training and operational data.
  - **Compliance Officers**: Ensure data processing meets quality standards and maintains unbiased outputs.

- **Ethical Considerations**: Preventing data poisoning ensures fairness and accuracy in model outputs, supporting user safety and ethical AI use.

- **TOGAF Domain Mapping**:
  - **Data Architecture**: Secure data pipelines and apply validation for incoming data sources.
  - **Technology Architecture**: Enforce monitoring tools to protect data integrity.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce data validation protocols and provenance tracking to ensure data quality.
  - **Detective Controls**:
    - Apply anomaly detection to training data to identify potential poisoning.
  - **Corrective Actions**:
    - Retrain models if significant poisoning is detected, ensuring data integrity is maintained.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Apply strict data integrity checks on training data.
  - **Monitoring Stage**: Continuously monitor data inputs to detect anomalies or poisoning attempts.

- **Recommended Tools**: Data provenance solutions, anomaly detection systems.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: Insecure output handling may lead to unfiltered LLM outputs disclosing sensitive information or executing unintended actions, such as unauthorized data disclosure or injection vulnerabilities.

- **Example Scenario**: A financial chatbot unintentionally discloses sensitive customer data due to inadequate output filtering.

- **Stakeholder Impact**:
  - **Developers**: Implement secure output filtering and encoding.
  - **Risk Managers**: Ensure data leakage risks are mitigated in all LLM outputs.
  - **Compliance Officers**: Ensure that outputs adhere to privacy and security regulations.

- **Ethical Considerations**: Preventing unauthorized disclosures through secure output handling upholds privacy, user trust, and compliance.

- **TOGAF Domain Mapping**:
  - **Data Architecture**: Implement policies to secure data outputs.
  - **Application Architecture**: Design safe response structures with built-in output filtering mechanisms.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encode and escape outputs to prevent data leaks and injection vulnerabilities.
  - **Detective Controls**:
    - Conduct audits on output handling and validate against security policies.
  - **Corrective Actions**:
    - Automatically redact or mask sensitive information found in outputs.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Enforce secure output handling protocols with ongoing validation.
  - **Monitoring Stage**: Continuously audit outputs for security risks.

- **Recommended Tools**: Output encoding libraries, secure formatting libraries, and data redaction tools.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to unintended autonomous actions by an LLM, which could lead to risky or unauthorized decisions, especially in high-stakes applications.

- **Example Scenario**: An LLM autonomously authorizes transactions above a certain threshold without requiring human approval, leading to potential financial risk.

- **Stakeholder Impact**:
  - **Developers**: Implement limitations on model autonomy.
  - **Architects**: Ensure that role-based permissions and approval mechanisms are integrated within application workflows.
  - **Risk Managers**: Monitor high-stakes actions to prevent unauthorized decision-making.

- **Ethical Considerations**: Limiting LLM autonomy promotes accountability and prevents unintended harm.

- **TOGAF Domain Mapping**:
  - **Business Architecture**: Define boundaries for acceptable actions by AI, aligned with organizational policies.
  - **Application Architecture**: Integrate role-based access and approval workflows for high-impact actions.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce least privilege for model actions, limiting autonomy in high-stakes scenarios.
    - Implement human-in-the-loop (HITL) for critical decisions.
  - **Detective Controls**:
    - Set alerts for autonomous actions that exceed predefined thresholds.
  - **Corrective Actions**:
    - Review incidents to refine role-based access control policies.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define limits on model autonomy.
  - **Deployment Stage**: Monitor autonomous actions with HITL controls.

- **Recommended Tools**: RBAC, HITL workflow systems, alerting tools.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompt leakage occurs when internal prompts that guide model behavior are exposed, allowing attackers to manipulate or bypass security controls.

- **Example Scenario**: An attacker accesses system prompts, manipulating responses to reveal sensitive information or bypass restrictions.

- **Stakeholder Impact**:
  - **Developers**: Securely manage prompt storage and restrict access.
  - **Risk Managers**: Protect against prompt exposure to prevent unauthorized access.
  - **Compliance Officers**: Ensure prompt handling complies with confidentiality standards.

- **Ethical Considerations**: Protecting prompts prevents unauthorized actions and supports reliable, secure interactions.

- **TOGAF Domain Mapping**:
  - **Data Architecture**: Define confidentiality requirements for prompt storage.
  - **Technology Architecture**: Implement access control and encryption for prompt data.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encrypt prompt storage and limit access to authorized personnel.
  - **Detective Controls**:
    - Implement access logging and regular monitoring for prompt access.
  - **Corrective Actions**:
    - Update prompt configurations if unauthorized access is detected.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Ensure prompt storage is secured and access-controlled.
  - **Monitoring Stage**: Continuously track and log access to prompt data.

- **Recommended Tools**: Secure configuration management tools, access management solutions, encryption libraries.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Weaknesses in data embeddings and vectors can lead to biased or adversarially manipulated outputs, compromising reliability and fairness.

- **Example Scenario**: Bias in embeddings used by a job-matching LLM results in unfair recommendations for certain demographic groups, potentially causing reputational harm and regulatory issues.

- **Stakeholder Impact**:
  - **Developers**: Ensure embeddings are managed securely to detect biases.
  - **Risk Managers**: Regularly assess embeddings for integrity and fairness.

- **Ethical Considerations**: Fairness in embeddings promotes equitable outcomes and aligns with ethical AI practices.

- **TOGAF Domain Mapping**:
  - **Data Architecture**: Monitor embeddings for integrity to prevent adversarial manipulation.
  - **Application Architecture**: Use bias detection controls to ensure fairness.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Conduct adversarial testing and apply bias detection on embeddings.
  - **Detective Controls**:
    - Continuously review embeddings for signs of manipulation or bias.
  - **Corrective Actions**:
    - Retrain embeddings if biases are detected.

- **Implementation Notes by AI Lifecycle**:
  - **Training Stage**: Conduct robust bias and fairness checks on embeddings.
  - **Post-Deployment**: Monitor embedding integrity over time.

- **Recommended Tools**: Fairlearn, Microsoft InterpretML.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation occurs when an LLM generates inaccurate or misleading information, especially critical in applications such as healthcare or finance.

- **Example Scenario**: A healthcare chatbot provides incorrect medical advice, potentially endangering users.

- **Stakeholder Impact**:
  - **Developers**: Implement verification mechanisms for high-stakes outputs.
  - **Risk Managers**: Monitor outputs for accuracy and consistency.

- **Ethical Considerations**: Delivering accurate information is essential for trust and safety.

- **TOGAF Domain Mapping**:
  - **Business Architecture**: Define policies and standards for high-stakes decisions.
  - **Data Architecture**: Validate data accuracy and consistency.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Cross-verify high-risk outputs with reliable sources.
  - **Detective Controls**:
    - Real-time validation of outputs, especially for sensitive applications.
  - **Corrective Actions**:
    - Adjust models if misinformation is identified.

- **Recommended Tools**: Verification platforms, cross-validation systems.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Unbounded resource consumption by LLMs can lead to degraded performance or denial of service, impacting system availability.

- **Example Scenario**: Excessive usage in a production system exhausts resources, causing slowdowns and affecting other services.

- **Stakeholder Impact**:
  - **Developers**: Implement rate limits to manage resource usage.
  - **Risk Managers**: Monitor system availability to prevent resource exhaustion.

- **Ethical Considerations**: Efficient resource management promotes service continuity and reliability.

- **TOGAF Domain Mapping**:
  - **Technology Architecture**: Monitor and control resource usage for reliability.
  - **Application Architecture**: Enforce rate limiting and load balancing.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply rate-limiting and load balancing.
  - **Detective Controls**:
    - Monitor usage patterns and detect spikes.
  - **Corrective Actions**:
    - Dynamically adjust limits to balance load during peak times.

- **Recommended Tools**: Rate-limiting solutions (e.g., Kong), load balancers, resource monitors (e.g., Prometheus).

---

OWASP Top 10 for LLM Applications 2025 mapped to TOGAF principles enhances enterprise-wide security, ensuring AI applications are designed and deployed with robust architectural safeguards. TOGAF’s Business, Data, Application, and Technology domains, organizations can address LLM vulnerabilities within a structured and strategic framework, building resilient AI systems that meet compliance, ethical, and operational requirements.

**Next Steps**:
1. **Enterprise Integration**: Leverage TOGAF’s architecture framework to assess and integrate AI-specific security measures into enterprise-wide systems.
2. **Continuous Monitoring**: Establish real-time monitoring and anomaly detection to track and respond to vulnerabilities dynamically.
3. **Cross-Department Collaboration**: Encourage collaboration across development, risk, and compliance teams to ensure holistic alignment with TOGAF and OWASP principles.

This alignment supports not only organizational resilience but also fosters trust and accountability in AI-driven initiatives.
