# OWASP Top 10 for Large Language Model Applications 2025 Mapped to PCI DSS

This repository provides an enhanced mapping of the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to [**PCI DSS**](https://www.pcisecuritystandards.org/standards/pci-dss/) requirements, covering **Build and Maintain a Secure Network and Systems**, **Protect Cardholder Data**, **Maintain a Vulnerability Management Program**, **Implement Strong Access Control Measures**, **Regularly Monitor and Test Networks**, and **Maintain an Information Security Policy**. This mapping supports security, compliance, and development teams in aligning LLM security practices with PCI DSS requirements to protect sensitive information, ensure compliance, and enhance risk management.

Each vulnerability includes real-world scenarios, stakeholder impacts, ethical considerations, granular risk mitigation steps, and specific guidance on implementing these practices within the AI lifecycle to maximize PCI DSS compliance.

| **Vulnerability**                         | **Risk Level** | **PCI DSS Requirements**                           | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|----------------|----------------------------------------------------|--------------------------------------------|---------------------------------------------------------|
| LLM01:2025 Prompt Injection               | High           | 1.1, 1.3, 6.1, 6.2, 12.1                           | Unauthorized actions, data exposure       | Input validation, prompt integrity enforcement          |
| LLM02:2025 Sensitive Information Disclosure | High          | 3.3, 3.4, 6.5.10, 8.7, 12.10                      | Disclosure of sensitive data              | Data masking, access controls                           |
| LLM03:2025 Supply Chain Vulnerabilities   | Medium         | 6.1, 6.2, 6.4, 12.8                               | Compromised dependencies                   | Dependency monitoring, supply chain risk assessment     |
| LLM04:2025 Data and Model Poisoning       | High           | 6.5, 6.6, 10.5, 12.5                              | Compromised data integrity, model biases   | Data integrity checks, secure data handling             |
| LLM05:2025 Insecure Output Handling       | Medium         | 6.5.10, 6.6, 10.2, 12.5                           | Unauthorized output actions                | Output filtering, standardized format requirements      |
| LLM06:2025 Excessive Agency               | Medium         | 7.1, 8.1, 10.1, 12.3                              | Unintended autonomous actions             | Least privilege, human approval for high-risk actions   |
| LLM07:2025 System Prompt Leakage          | Medium         | 3.4, 8.3, 10.6, 12.1                              | Unauthorized prompt exposure               | Secure prompt storage, access restrictions              |
| LLM08:2025 Vector and Embedding Weaknesses | Medium         | 6.5, 10.5, 12.10                                  | Biased or malicious outputs                | Bias testing, secure vector storage                     |
| LLM09:2025 Misinformation                 | Medium         | 6.5, 6.6, 10.6, 12.10                             | Inaccurate or misleading content          | Cross-verification, human oversight                     |
| LLM10:2025 Unbounded Consumption          | Low            | 2.2, 10.2, 11.4, 12.5                             | Resource exhaustion, degraded performance  | Rate-limiting, load balancing                           |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Attackers manipulate prompt inputs to alter model behavior, potentially enabling unauthorized actions, disclosing sensitive information, or bypassing security controls.

- **Example Scenario**: A customer service LLM chatbot is manipulated by a prompt injection attack, causing it to reveal sensitive customer information.

- **Stakeholder Impact**:
  - **Developers**: Need to apply secure coding and input validation to prevent prompt injection.
  - **Security Analysts**: Responsible for implementing and monitoring safeguards against prompt manipulation.
  - **Risk Managers**: Address potential compliance and data exposure risks.
  - **Compliance Officers**: Ensure adherence to PCI DSS requirements to mitigate the risk of unauthorized prompt manipulation.

- **Ethical Considerations**: Protecting prompt handling upholds user data security, prevents unauthorized access, and strengthens trust in financial transactions.

- **PCI DSS Mapping**:
  - **Requirement 1.1**: Create a network configuration policy that limits unauthorized prompt access.
  - **Requirement 1.3**: Prohibit direct public access between external and internal systems to prevent prompt injections.
  - **Requirement 6.1**: Conduct regular vulnerability assessments focused on prompt security.
  - **Requirement 6.2**: Apply patches or security updates promptly when prompt-related vulnerabilities are identified.
  - **Requirement 12.1**: Establish and maintain security policies that address prompt handling security.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Implement input validation with strict constraints on acceptable prompt formats.
    - Segment prompt-related functions to limit their access and isolate prompt processing environments.
  - **Detective Controls**:
    - Continuously monitor and log prompt inputs to identify anomalous or potentially malicious activity.
    - Use behavioral analytics to detect and flag unusual prompt patterns indicative of injection attempts.
  - **Corrective Actions**:
    - Quarantine suspicious inputs and revalidate prompt security policies periodically.
    - Update security rules in response to any detected prompt injection attempts and apply corrective patches as necessary.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define prompt security requirements, including input validation rules and acceptable formats.
  - **Deployment Stage**: Continuously monitor prompt inputs for any indicators of compromise.

- **Recommended Tools**: OWASP ZAP, regex validators, boundary-checking tools, and SIEM systems for real-time monitoring.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Sensitive information disclosure occurs when an LLM unintentionally reveals private data, including cardholder data, due to weak access controls or inadequate data masking.

- **Example Scenario**: A healthcare chatbot inadvertently reveals credit card data due to insufficient data masking protocols.

- **Stakeholder Impact**:
  - **Developers**: Must implement secure output handling to prevent exposure of sensitive data.
  - **IT Security Teams**: Responsible for encrypting and masking sensitive data and ensuring secure storage.
  - **Data Privacy Officers**: Ensure compliance with PCI DSS data protection guidelines.

- **Ethical Considerations**: Safeguarding sensitive data helps maintain privacy, trust, and regulatory compliance.

- **PCI DSS Mapping**:
  - **Requirement 3.3**: Mask PAN when displayed, following PCI DSS display guidelines.
  - **Requirement 3.4**: Use strong cryptography to render PAN unreadable wherever stored.
  - **Requirement 6.5.10**: Prevent data leakage vulnerabilities that could lead to sensitive data exposure.
  - **Requirement 8.7**: Restrict access to sensitive cardholder data.
  - **Requirement 12.10**: Maintain an incident response plan to address any data leakage issues promptly.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply cryptography to render all sensitive information unreadable and enforce output masking for PAN.
    - Segment sensitive information to reduce the risk of accidental exposure.
  - **Detective Controls**:
    - Regularly review and audit access logs to identify unauthorized data access or potential leaks.
  - **Corrective Actions**:
    - Mask or redact any disclosed sensitive information immediately upon detection.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Ensure that any collected sensitive data is anonymized or encrypted.
  - **Deployment Stage**: Continuously audit data handling practices for PCI DSS compliance.

- **Recommended Tools**: Data masking tools, encryption libraries (AES), PCI DSS-compliant cryptographic libraries, and monitoring solutions.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Supply chain vulnerabilities stem from unvetted third-party dependencies, which may introduce potential vulnerabilities that compromise LLM security.

- **Example Scenario**: A third-party dependency contains a vulnerability that opens the application to data breaches or unauthorized access.

- **Stakeholder Impact**:
  - **Developers**: Need to verify and secure third-party libraries and dependencies.
  - **Risk Managers**: Assess risks posed by external dependencies on the application.
  - **Compliance Officers**: Ensure vendor compliance with PCI DSS security requirements.

- **Ethical Considerations**: Maintaining secure third-party components protects data integrity and user trust.

- **PCI DSS Mapping**:
  - **Requirement 6.1**: Identify vulnerabilities in third-party components and apply patches.
  - **Requirement 6.2**: Continuously monitor for and patch vulnerabilities in dependencies.
  - **Requirement 6.4**: Ensure secure deployment practices for third-party integrations.
  - **Requirement 12.8**: Maintain and monitor a list of service providers to assess vendor risk.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Require attestations from third-party vendors that their software complies with PCI DSS.
    - Maintain a list of approved third-party libraries and dependencies, verifying their compliance regularly.
  - **Detective Controls**:
    - Use software composition analysis tools to continuously scan dependencies for vulnerabilities.
  - **Corrective Actions**:
    - Isolate or replace vulnerable third-party components promptly.

- **Implementation Notes by AI Lifecycle**:
  - **Development Stage**: Vet and validate dependencies for security compliance before deployment.
  - **Deployment Stage**: Regularly audit third-party integrations to ensure continued compliance.

- **Recommended Tools**: Dependency management tools (e.g., Snyk, OWASP Dependency-Check), vendor risk management systems, and software composition analysis tools.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data poisoning attacks manipulate training datasets, potentially leading to biased or incorrect outputs, which can affect the reliability of LLMs.

- **Example Scenario**: A model trained on manipulated data provides biased or erroneous predictions.

- **Stakeholder Impact**:
  - **Developers**: Implement data validation controls to prevent tampering.
  - **Risk Managers**: Monitor the integrity of training data to detect data poisoning attempts.
  - **Compliance Officers**: Verify compliance with PCI DSS requirements to secure sensitive data.

- **Ethical Considerations**: Ensuring data integrity prevents biased or malicious outputs, promoting fair and accurate results.

- **PCI DSS Mapping**:
  - **Requirement 6.5**: Use secure coding practices to protect against tampering.
  - **Requirement 6.6**: Test applications for data manipulation vulnerabilities.
  - **Requirement 10.5**: Protect logs and audit trails to maintain data integrity.
  - **Requirement 12.5**: Implement monitoring for data poisoning indicators and anomalies.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Use data validation and segmentation to prevent poisoning.
  - **Detective Controls**:
    - Set up anomaly detection systems to identify outliers or unusual patterns in data.
  - **Corrective Actions**:
    - Retrain models with validated data if signs of poisoning are detected.

- **Implementation Notes by AI Lifecycle**:
  - **Data Collection Stage**: Enforce data integrity checks and use secure ingestion pipelines.
  - **Training Stage**: Continuously monitor datasets for poisoning attempts.

- **Recommended Tools**: Data validation and segmentation tools, anomaly detection solutions, and secure data handling protocols.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: Insecure output handling may lead to unfiltered LLM outputs that disclose sensitive information or execute unintended actions, such as unauthorized data exposure or injection vulnerabilities.

- **Example Scenario**: A customer service LLM unintentionally discloses credit card information in response to a user query due to insufficient output filtering.

- **Stakeholder Impact**:
  - **Developers**: Must implement secure output handling and filtering mechanisms.
  - **IT Security Teams**: Ensure output security to avoid data leakage and maintain PCI DSS compliance.
  - **Compliance Officers**: Monitor data handling practices to prevent unauthorized data disclosures.

- **Ethical Considerations**: Ensuring secure output handling protects sensitive data, upholds compliance, and prevents unauthorized disclosures.

- **PCI DSS Mapping**:
  - **Requirement 6.5.10**: Prevent data leakage vulnerabilities in application design.
  - **Requirement 6.6**: Implement security controls to protect applications from malicious input and output.
  - **Requirement 10.2**: Log access to all data to monitor for unauthorized disclosures.
  - **Requirement 12.5**: Establish procedures to regularly review and manage secure output practices.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply secure encoding and filtering to outputs to prevent data leakage.
    - Define clear guidelines for acceptable output formats and implement them during development.
  - **Detective Controls**:
    - Audit outputs periodically to detect potential sensitive information disclosures.
    - Log and monitor output events to identify unauthorized disclosures.
  - **Corrective Actions**:
    - Flag and redact any sensitive information detected in outputs.
    - Update output handling policies to reinforce secure data practices.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Enforce secure output handling protocols to comply with PCI DSS requirements.
  - **Post-Deployment**: Continuously monitor and audit output data for potential security risks.

- **Recommended Tools**: Secure encoding libraries, data redaction tools, output filtering libraries, and logging solutions.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to unintended autonomous actions taken by an LLM, which could lead to unauthorized actions or decisions in critical areas, such as financial transactions.

- **Example Scenario**: An LLM independently approves high-value transactions without human oversight, exposing the organization to financial risks.

- **Stakeholder Impact**:
  - **Developers**: Limit LLM permissions to prevent excessive autonomy.
  - **Risk Managers**: Enforce approval controls for high-stakes actions.
  - **Compliance Officers**: Ensure that access controls align with PCI DSS policies to prevent unauthorized actions.

- **Ethical Considerations**: Limiting model autonomy promotes accountability, minimizes risks, and aligns with responsible AI practices.

- **PCI DSS Mapping**:
  - **Requirement 7.1**: Limit access to systems and data on a need-to-know basis.
  - **Requirement 8.1**: Assign unique IDs to control access and monitor all personnel actions.
  - **Requirement 10.1**: Track all access to system components, ensuring monitoring of autonomous actions.
  - **Requirement 12.3**: Implement access control measures that require human oversight for critical decisions.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Enforce the principle of least privilege for all LLM actions.
    - Implement human-in-the-loop (HITL) controls to require human approval for high-risk actions.
  - **Detective Controls**:
    - Monitor logs and set up alerts for unauthorized or autonomous high-value actions.
  - **Corrective Actions**:
    - Investigate and adjust access policies in response to any unauthorized autonomous actions.

- **Implementation Notes by AI Lifecycle**:
  - **Design Stage**: Define autonomy limits for the LLM to restrict unauthorized actions.
  - **Deployment Stage**: Continuously monitor high-risk actions to ensure compliance with PCI DSS access policies.

- **Recommended Tools**: Role-Based Access Control (RBAC), HITL workflow tools, monitoring and alerting systems.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompt leakage occurs when internal prompts that guide an LLM’s behavior are exposed, allowing attackers to manipulate the model’s responses or bypass security controls.

- **Example Scenario**: An attacker accesses system prompts and manipulates them to bypass access restrictions and access sensitive data.

- **Stakeholder Impact**:
  - **Developers**: Must secure prompt storage and implement access controls.
  - **IT Security Teams**: Responsible for ensuring prompt data is encrypted and protected.
  - **Compliance Officers**: Ensure system prompt handling aligns with confidentiality and access control standards.

- **Ethical Considerations**: Protecting system prompts ensures secure interactions, reduces unauthorized access, and promotes trust in AI applications.

- **PCI DSS Mapping**:
  - **Requirement 3.4**: Render sensitive data unreadable, including prompts, where applicable.
  - **Requirement 8.3**: Implement strong authentication measures for access to prompt storage.
  - **Requirement 10.6**: Review all access logs to detect unauthorized prompt access.
  - **Requirement 12.1**: Develop policies to protect sensitive information, including prompts.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Encrypt prompt storage and restrict access to essential personnel only.
    - Use multi-factor authentication (MFA) to secure access to prompt data.
  - **Detective Controls**:
    - Log and review prompt access events to detect and respond to unauthorized access.
  - **Corrective Actions**:
    - Update or replace exposed prompts and adjust access controls to prevent future leaks.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Ensure prompts are encrypted and stored securely, with limited access.
  - **Monitoring Stage**: Continuously monitor prompt access logs to detect anomalies.

- **Recommended Tools**: Encryption libraries, access management solutions, MFA, and SIEM systems for logging.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Weaknesses in embeddings and vectors can lead to biased or adversarial outputs, compromising the reliability and fairness of LLM responses.

- **Example Scenario**: Bias in embeddings in a fraud detection model leads to unfair treatment of certain demographics.

- **Stakeholder Impact**:
  - **Developers**: Ensure embeddings are managed securely and are free from bias.
  - **Data Scientists**: Regularly assess embeddings for biases and adversarial manipulation.
  - **Compliance Officers**: Confirm that data handling practices comply with PCI DSS and do not result in biased outputs.

- **Ethical Considerations**: Ensuring fairness in embeddings supports equitable AI practices and helps build a trusted application.

- **PCI DSS Mapping**:
  - **Requirement 6.5**: Implement secure coding practices to protect against data tampering.
  - **Requirement 10.5**: Protect logs and audit trails to maintain embedding integrity.
  - **Requirement 12.10**: Establish procedures to handle detected biases or embedding issues.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Conduct bias testing and adversarial testing on embeddings before deployment.
    - Store embeddings securely and manage access to prevent manipulation.
  - **Detective Controls**:
    - Regularly monitor and review embeddings for signs of bias or adversarial manipulation.
  - **Corrective Actions**:
    - Retrain embeddings if biases or integrity issues are detected, and adjust handling policies.

- **Implementation Notes by AI Lifecycle**:
  - **Training Stage**: Implement thorough bias testing during embedding training.
  - **Post-Deployment**: Continuously monitor embeddings to ensure ongoing integrity.

- **Recommended Tools**: Bias detection tools, secure storage solutions for embeddings, adversarial testing frameworks.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation occurs when an LLM generates inaccurate or misleading information, which can be especially harmful in applications like financial services.

- **Example Scenario**: A financial advice LLM provides incorrect recommendations that lead to potentially harmful decisions.

- **Stakeholder Impact**:
  - **Developers**: Implement validation and verification processes for high-risk outputs.
  - **Risk Managers**: Monitor outputs for accuracy, especially in sensitive domains.
  - **Compliance Officers**: Ensure that output quality complies with PCI DSS guidelines and does not mislead users.

- **Ethical Considerations**: Delivering accurate and reliable information is essential for maintaining trust and ethical use of AI in high-stakes applications.

- **PCI DSS Mapping**:
  - **Requirement 6.5**: Secure coding practices to prevent misinformation vulnerabilities.
  - **Requirement 6.6**: Test and review application logic to ensure accurate output.
  - **Requirement 10.6**: Review and log high-stakes outputs to detect any misinformation.
  - **Requirement 12.10**: Establish an incident response procedure to address misinformation issues promptly.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Implement cross-verification techniques to ensure accuracy in high-risk outputs.
  - **Detective Controls**:
    - Set up real-time monitoring and validation of outputs in sensitive fields.
  - **Corrective Actions**:
    - Adjust models and retrain if inaccuracies are found, and update information verification policies.

- **Implementation Notes by AI Lifecycle**:
  - **Training Stage**: Ensure training data is high quality and verified.
  - **Post-Deployment**: Continuously validate outputs, particularly in sensitive applications like finance.

- **Recommended Tools**: Verification platforms, real-time monitoring systems, cross-validation solutions.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Unbounded resource consumption by LLMs can lead to degraded performance or denial of service (DoS), impacting system availability and compliance with service standards.

- **Example Scenario**: A payment processing system experiences slowdowns due to excessive LLM usage, affecting transaction processing.

- **Stakeholder Impact**:
  - **Developers**: Implement controls to limit resource usage by LLMs.
  - **System Administrators**: Ensure system performance meets PCI DSS availability standards.
  - **Compliance Officers**: Confirm that resource management practices align with PCI DSS requirements to prevent DoS issues.

- **Ethical Considerations**: Efficient resource management promotes continuous service availability and maintains user trust.

- **PCI DSS Mapping**:
  - **Requirement 2.2**: Develop configuration standards for consistent resource management.
  - **Requirement 10.2**: Log resource access and monitor for potential overloads.
  - **Requirement 11.4**: Regularly test system performance to ensure availability.
  - **Requirement 12.5**: Define roles and responsibilities for resource management.

- **Mitigation Strategy Framework**:
  - **Preventive Measures**:
    - Apply rate-limiting, load balancing, and quotas to prevent excessive consumption.
  - **Detective Controls**:
    - Continuously monitor resource usage patterns and detect anomalies.
  - **Corrective Actions**:
    - Adjust system configurations to handle peak usage times and prevent DoS.

- **Implementation Notes by AI Lifecycle**:
  - **Deployment Stage**: Set up rate-limiting and load balancing mechanisms.
  - **Post-Deployment**: Monitor for excessive usage patterns to maintain availability.

- **Recommended Tools**: Rate-limiting solutions, load balancers, resource monitoring platforms like Prometheus.

---

The OWASP Top 10 for LLM Applications 2025 mapped to PCI DSS standards provides organizations with a roadmap for secure, compliant, and resilient AI systems that handle sensitive cardholder data. This mapping highlights how LLM vulnerabilities intersect with PCI DSS requirements, allowing teams to implement targeted mitigations, prevent unauthorized actions, and maintain robust data security.

**Next Steps**:
1. **Continuous Compliance Monitoring**: Utilize monitoring and alerting systems to detect and resolve potential vulnerabilities in real-time.
2. **Frequent Testing and Review**: Schedule regular scans and tests to verify ongoing PCI DSS compliance of LLM applications.
3. **Collaboration Across Teams**: Promote active collaboration between compliance, IT, and security teams to maintain PCI DSS-compliant AI systems.

This alignment builds a foundation of secure AI practices that protect sensitive information, foster trust, and enhance organizational resilience.
