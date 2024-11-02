# OWASP Top 10 for Large Language Model Applications 2025 Mapped to NIST AI RMF 1.0 (AI 100-1)

This repository provides a detailed mapping of the vulnerabilities outlined in the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to [**NIST AI RMF 1.0 (AI 100-1)**](https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-development) standards. This mapping supports developers, risk managers, and security teams in aligning AI-specific security practices with NIST AI RMF’s core functions, promoting trustworthy, safe, and responsible AI applications.

Each vulnerability includes example scenarios, the impact on various stakeholders, ethical considerations, relevant tools, and guidance for integrating these practices into the AI lifecycle.

| **Vulnerability**                         | **Risk Level** | **NIST AI RMF Core Functions**                        | **Key Risks**                              | **Top Mitigation Steps**                                |
|-------------------------------------------|------------|--------------------------------------------------|----------------------------------------|-----------------------------------------------------|
| LLM01:2025 Prompt Injection               | High       | Map, Manage, Govern                                 | Unauthorized access, data leakage      | Strict input validation, enforce prompt integrity    |
| LLM02:2025 Sensitive Information Disclosure | High       | Govern, Map, Manage                                | Exposure of sensitive information      | Data masking, access controls                       |
| LLM03:2025 Supply Chain Vulnerabilities   | Medium     | Govern, Manage, Map                                | Malicious components, unverified dependencies | Regular audits, use of dependency monitoring tools   |
| LLM04:2025 Data and Model Poisoning       | High       | Manage, Measure, Govern                            | Compromised training data, incorrect outputs | Data audits, secure data pipelines                  |
| LLM05:2025 Insecure Output Handling       | Medium     | Govern, Manage, Measure                            | Data leakage, injection vulnerabilities | Output filtering, output format definitions         |
| LLM06:2025 Excessive Agency               | Medium     | Govern, Manage, Map                                | Unintended autonomous actions          | Enforce least privilege, human approval for high-risk actions |
| LLM07:2025 System Prompt Leakage          | Medium     | Govern, Manage, Map                                | System prompt exposure                 | Conceal system prompts, implement secure configurations |
| LLM08:2025 Vector and Embedding Weaknesses | Medium     | Manage, Measure, Govern                            | Biased or malicious outputs            | Adversarial testing, secure vector storage          |
| LLM09:2025 Misinformation                 | Medium     | Govern, Measure, Map                               | Inaccurate or misleading content      | Cross-verification, human oversight                  |
| LLM10:2025 Unbounded Consumption          | Low        | Govern, Manage, Measure                            | Excessive resource usage, denial of service | Rate-limiting, load balancing                       |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

- **Description**: Prompt injection occurs when an attacker manipulates LLM prompts to modify model behavior, leading to potential unauthorized access, data leakage, and system misconfigurations. It is particularly risky in open-ended systems where user inputs directly influence output generation.

- **Example Scenario**: A customer support chatbot is manipulated by a prompt injection attack, causing it to reveal sensitive information about other customers.

- **Stakeholder Impact**: 
  - **Developers**: Need to implement prompt validation and enforce security constraints.
  - **Risk Managers**: Concerned with the potential of unauthorized access and regulatory violations.
  - **Compliance Officers**: Focus on securing data privacy to avoid legal implications.

- **Ethical Considerations**: Ensuring that LLMs do not reveal unauthorized or harmful information safeguards user trust and privacy.

- **NIST AI RMF Mapping**:
  - **Map**: Identify and document prompt vulnerabilities and manipulation risks.
  - **Manage**: Implement secure prompt-handling processes and strict input validation.
  - **Govern**: Establish policies on acceptable prompt structures and validation protocols.

- **Mitigation Strategies**:
  1. Define and validate prompt constraints using strict input validation tools (e.g., OWASP ZAP).
  2. Apply rule-based validation for accepted prompt formats to detect anomalies.
  3. Regularly monitor LLM behavior for signs of unexpected outputs.

- **Recommended Tools**: OWASP ZAP, regular expression validators, prompt integrity frameworks

- **AI Lifecycle Notes**: Addressed during **deployment** and **post-deployment monitoring** to ensure prompt constraints are enforced continuously.

- **Key Risks**: Unauthorized access, data leakage, model manipulation
- **Top Mitigation Steps**: Strict input validation, enforce prompt integrity

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

- **Description**: Sensitive information disclosure occurs when an LLM unintentionally reveals private data, including PII or proprietary content, due to inadequate access control or insufficient filtering mechanisms.

- **Example Scenario**: A healthcare chatbot inadvertently reveals a patient's medical information due to insufficient data masking.

- **Stakeholder Impact**: 
  - **Developers**: Responsible for implementing data masking and access controls.
  - **Risk Managers**: Need to ensure sensitive information is adequately protected to mitigate legal and reputational risks.
  - **Compliance Officers**: Must comply with regulations like GDPR and HIPAA for data privacy.

- **Ethical Considerations**: Protecting user privacy is critical to upholding ethical standards in AI.

- **NIST AI RMF Mapping**:
  - **Govern**: Establish privacy policies and access controls.
  - **Map**: Identify data points vulnerable to exposure.
  - **Manage**: Implement mechanisms like data masking and redaction.

- **Mitigation Strategies**:
  1. Enforce data masking for sensitive information with tools like Google’s TensorFlow Privacy.
  2. Implement logging to track access to sensitive data.
  3. Conduct regular audits to ensure compliance with data privacy standards.

- **Recommended Tools**: TensorFlow Privacy, data masking tools, differential privacy frameworks

- **AI Lifecycle Notes**: Essential during **data collection** and **deployment** stages to ensure sensitive data is never exposed.

- **Key Risks**: Exposure of sensitive information, legal non-compliance
- **Top Mitigation Steps**: Data masking, access controls, audit trails

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

- **Description**: Supply chain vulnerabilities stem from third-party dependencies that, if unvetted, may introduce malicious elements or unaddressed vulnerabilities into the system.

- **Example Scenario**: A dependency in the LLM's language model library has a known vulnerability that allows remote code execution.

- **Stakeholder Impact**: 
  - **Developers**: Must vet and verify the security of each component.
  - **Risk Managers**: Concerned with managing third-party risk and ensuring secure supply chains.
  - **Compliance Officers**: Responsible for enforcing third-party security policies.

- **Ethical Considerations**: Trustworthy AI requires secure, transparent supply chains to maintain user confidence.

- **NIST AI RMF Mapping**:
  - **Govern**: Establish security requirements for supply chain components.
  - **Manage**: Conduct dependency assessments and verify component integrity.
  - **Map**: Identify all dependencies and maintain a comprehensive inventory.

- **Mitigation Strategies**:
  1. Conduct regular audits of third-party dependencies.
  2. Require security attestations for critical third-party software.
  3. Use software composition analysis tools for dependency security.

- **Recommended Tools**: OWASP Dependency-Check, Snyk, Veracode

- **AI Lifecycle Notes**: Addressed during **design** and **development**, with periodic **post-deployment reviews**.

- **Key Risks**: Malicious components, unverified dependencies
- **Top Mitigation Steps**: Regular audits, dependency monitoring tools, supply chain security policies

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

- **Description**: Data and model poisoning attacks inject malicious data into training or input datasets, skewing model predictions or introducing biases.

- **Example Scenario**: An attacker poisons the dataset used for financial predictions, causing the model to give biased or harmful advice.

- **Stakeholder Impact**: 
  - **Developers**: Need to implement data validation and pipeline security.
  - **Risk Managers**: Monitor for potential integrity breaches in the training data.
  - **Compliance Officers**: Ensure data integrity to avoid biased outcomes.

- **Ethical Considerations**: Ensuring data integrity supports unbiased, fair outcomes and helps prevent harmful consequences.

- **NIST AI RMF Mapping**:
  - **Manage**: Secure data ingestion processes and validate data integrity.
  - **Measure**: Monitor data quality and detect anomalies.
  - **Govern**: Establish data validation protocols to prevent malicious inputs.

- **Mitigation Strategies**:
  1. Use anomaly detection to identify potentially poisoned data.
  2. Implement data provenance and version control.
  3. Apply adversarial testing and robustness techniques.

- **Recommended Tools**: Anomaly detection tools, data provenance solutions, adversarial robustness frameworks

- **AI Lifecycle Notes**: Critical during **data collection** and **training**, with **ongoing monitoring** post-deployment.

- **Key Risks**: Compromised training data, incorrect outputs
- **Top Mitigation Steps**: Data audits, secure data pipelines, adversarial testing

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)

- **Description**: Insecure output handling may result in unfiltered LLM outputs that disclose sensitive information or perform unintended actions (e.g., HTML injection). Outputs must be filtered and validated to prevent data leakage and other vulnerabilities.

- **Example Scenario**: A financial chatbot discloses sensitive customer data in its responses due to improper output filtering.

- **Stakeholder Impact**:
  - **Developers**: Responsible for implementing secure output handling and formatting.
  - **Risk Managers**: Concerned with data leakage and reputation risks.
  - **Compliance Officers**: Focus on ensuring that outputs meet privacy and security regulations.

- **Ethical Considerations**: Preventing unauthorized data disclosures upholds user privacy and trust.

- **NIST AI RMF Mapping**:
  - **Govern**: Define policies for secure output handling and information disclosure.
  - **Manage**: Enforce output filtering and secure formatting protocols.
  - **Measure**: Regularly test output handling mechanisms to identify weaknesses.

- **Mitigation Strategies**:
  1. Use output encoding and escaping to prevent injection attacks.
  2. Apply secure response templates and enforce strict output formatting.
  3. Continuously monitor and audit outputs for potential security risks.

- **Recommended Tools**: OWASP Output Encoding Libraries, Secure Formatting Libraries, Data Redaction Tools

- **AI Lifecycle Notes**: Addressed during **deployment** and **post-deployment monitoring** to ensure secure handling across all outputs.

- **Key Risks**: Data leakage, injection vulnerabilities, unauthorized data disclosures
- **Top Mitigation Steps**: Output filtering, secure formatting, continuous audits

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)

- **Description**: Excessive agency refers to the unintended autonomous actions taken by an LLM, which could lead to harmful or unauthorized decisions. This is particularly relevant in applications where LLMs have the potential to make consequential decisions autonomously.

- **Example Scenario**: An AI assistant autonomously processes high-value transactions without human approval, posing financial risks.

- **Stakeholder Impact**:
  - **Developers**: Must enforce strict role-based access controls and define model boundaries.
  - **Risk Managers**: Focused on monitoring and limiting the model’s autonomy to prevent unintended actions.
  - **Compliance Officers**: Need to ensure the model does not exceed its intended scope, especially in regulated environments.

- **Ethical Considerations**: Limiting model autonomy supports accountability and prevents unintended harm.

- **NIST AI RMF Mapping**:
  - **Govern**: Define boundaries for AI autonomy and require human oversight for high-risk actions.
  - **Manage**: Use role-based access controls and approval mechanisms for high-stakes decisions.
  - **Map**: Identify potential high-risk actions that should require human intervention.

- **Mitigation Strategies**:
  1. Enforce the principle of least privilege, restricting the model’s permissions.
  2. Implement a human-in-the-loop process for high-impact decisions.
  3. Set clear boundaries for model autonomy based on application needs.

- **Recommended Tools**: Role-Based Access Control (RBAC) systems, Human Approval Workflow Tools

- **AI Lifecycle Notes**: Crucial in the **deployment** phase and **post-deployment monitoring** for controlled autonomy.

- **Key Risks**: Unauthorized decisions, safety risks, unintended model behaviors
- **Top Mitigation Steps**: Enforce least privilege, human approval, role-based access controls

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

- **Description**: System prompt leakage occurs when internal prompts that guide the model’s responses are exposed, allowing attackers to manipulate or bypass security controls.

- **Example Scenario**: An attacker gains access to system prompts, allowing them to alter the LLM’s behavior and bypass restrictions.

- **Stakeholder Impact**:
  - **Developers**: Responsible for securing prompt data and ensuring proper access controls.
  - **Risk Managers**: Concerned with unauthorized prompt access that could compromise security controls.
  - **Compliance Officers**: Need to enforce confidentiality of system prompts as part of secure system configuration.

- **Ethical Considerations**: Protecting system prompts prevents unauthorized manipulation, supporting reliable and secure interactions.

- **NIST AI RMF Mapping**:
  - **Govern**: Establish policies to protect and control access to system prompts.
  - **Manage**: Secure prompts in a protected environment with strict access controls.
  - **Map**: Identify sensitive prompt data and restrict access to authorized personnel only.

- **Mitigation Strategies**:
  1. Use secure storage solutions for system prompts, restricting access to essential personnel.
  2. Implement access controls and encrypt prompt data to prevent unauthorized access.
  3. Conduct periodic reviews of prompt configurations to ensure alignment with security policies.

- **Recommended Tools**: Secure Configuration Management Tools, Access Management Solutions, Encryption Libraries

- **AI Lifecycle Notes**: Critical during **deployment** and **post-deployment monitoring** to prevent unauthorized prompt access.

- **Key Risks**: Unauthorized prompt access, model manipulation
- **Top Mitigation Steps**: Secure prompt storage, access control, policy compliance checks

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)

- **Description**: Weaknesses in data embeddings and vectors can lead to biased or adversarially manipulated outputs, impacting model reliability and fairness.

- **Example Scenario**: Bias in embeddings causes a job-matching LLM to produce recommendations that favor certain demographics unfairly.

- **Stakeholder Impact**:
  - **Developers**: Must implement bias detection and secure embedding management.
  - **Risk Managers**: Concerned with ensuring unbiased outputs and minimizing reputational risks.
  - **Compliance Officers**: Responsible for validating model outputs for fairness and regulatory compliance.

- **Ethical Considerations**: Ensuring fairness in embeddings upholds ethical AI principles and promotes equitable outcomes.

- **NIST AI RMF Mapping**:
  - **Manage**: Apply robust techniques to ensure embedding quality and detect biases.
  - **Measure**: Regularly assess embeddings for bias and adversarial vulnerabilities.
  - **Govern**: Establish guidelines for secure and fair embedding management.

- **Mitigation Strategies**:
  1. Conduct adversarial testing to identify vulnerabilities in embeddings.
  2. Use bias detection tools to evaluate and mitigate any bias present in embeddings.
  3. Securely store and manage embeddings to prevent unauthorized modifications.

- **Recommended Tools**: Fairlearn, Microsoft InterpretML, Secure Storage Solutions for Vectors

- **AI Lifecycle Notes**: Addressed during **training** to ensure embedding integrity, with **post-deployment monitoring** for ongoing fairness assessments.

- **Key Risks**: Biased outputs, model manipulation, reduced trustworthiness
- **Top Mitigation Steps**: Adversarial testing, secure vector storage, bias detection

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

- **Description**: Misinformation occurs when an LLM generates incorrect or misleading information, which can lead to trust issues, especially in critical applications like healthcare or finance.

- **Example Scenario**: A healthcare chatbot provides incorrect medical advice, leading to potential harm to users.

- **Stakeholder Impact**:
  - **Developers**: Responsible for implementing verification mechanisms for high-stakes outputs.
  - **Risk Managers**: Concerned with monitoring outputs for accuracy and mitigating misinformation risks.
  - **Compliance Officers**: Need to ensure outputs meet accuracy standards, particularly in regulated industries.

- **Ethical Considerations**: Accurate information delivery is essential to maintain trust and ensure the safe use of AI.

- **NIST AI RMF Mapping**:
  - **Govern**: Define guidelines for generating reliable and accurate outputs.
  - **Measure**: Continuously monitor and validate outputs to prevent misinformation.
  - **Map**: Identify scenarios where misinformation could lead to significant harm and assess risks.

- **Mitigation Strategies**:
  1. Use cross-verification with trusted sources to validate outputs, especially in sensitive fields.
  2. Implement human oversight for high-stakes or high-risk responses.
  3. Apply retrieval-augmented generation techniques to improve accuracy.

- **Recommended Tools**: Cross-Verification Tools, Retrieval-Augmented Generation (RAG) Techniques

- **AI Lifecycle Notes**: Key in the **training** phase to ensure high-quality data and **post-deployment monitoring** for real-time validation.

- **Key Risks**: Inaccurate information, erosion of user trust, regulatory non-compliance
- **Top Mitigation Steps**: Cross-verification, human oversight, factual consistency checks

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

- **Description**: Unbounded consumption refers to excessive resource usage by LLMs, potentially leading to denial of service (DoS) and degraded system performance. Effective resource management is essential for scalability and reliability.

- **Example Scenario**: A chatbot API experiences an unanticipated spike in usage, exhausting resources and resulting in downtime.

- **Stakeholder Impact**:
  - **Developers**: Need to implement resource-limiting features.
  - **Risk Managers**: Focus on maintaining system availability and preventing DoS incidents.
  - **Compliance Officers**: Must ensure service reliability, especially in SLAs with strict uptime requirements.

- **Ethical Considerations**: Efficient resource management supports reliable service delivery, benefiting users and maintaining trust.

- **NIST AI RMF Mapping**:
  - **Govern**: Establish policies for efficient resource allocation and usage.
  - **Manage**: Implement monitoring and controls to prevent excessive usage.
  - **Measure**: Continuously assess system load and resource usage to prevent DoS risks.

- **Mitigation Strategies**:
  1. Apply rate limiting and load balancing to manage high-traffic scenarios.
  2. Use resource monitoring tools to detect and manage sudden usage spikes.
  3. Conduct performance audits and scalability tests to optimize resource use.

- **Recommended Tools**: Rate Limiting Tools (e.g., Kong), Load Balancing Solutions, Resource Monitoring (e.g., Prometheus)

- **AI Lifecycle Notes**: Essential during **deployment** and **post-deployment monitoring** to ensure sustained performance.

- **Key Risks**: Denial of service, resource exhaustion, degraded performance
- **Top Mitigation Steps**: Rate-limiting, load balancing, resource monitoring

---

### Summary Table: AI Lifecycle and Recommended Tools

| **Vulnerability**                         | **AI Lifecycle Stage**               | **Recommended Tools**                                      |
|-------------------------------------------|--------------------------------------|------------------------------------------------------------|
| LLM01:2025 Prompt Injection               | Deployment, Post-Deployment          | OWASP ZAP, Regex Validators                                |
| LLM02:2025 Sensitive Information Disclosure | Data Collection, Deployment          | TensorFlow Privacy, Data Masking Tools                     |
| LLM03:2025 Supply Chain Vulnerabilities   | Design, Development, Post-Deployment | OWASP Dependency-Check, Snyk, Veracode                     |
| LLM04:2025 Data and Model Poisoning       | Data Collection, Training, Monitoring| Anomaly Detection, Data Provenance Solutions               |
| LLM05:2025 Insecure Output Handling       | Deployment, Monitoring               | Output Encoding Tools, Secure Formatting Libraries         |
| LLM06:2025 Excessive Agency               | Deployment, Monitoring               | Role-Based Access Controls, Human Approval Systems         |
| LLM07:2025 System Prompt Leakage          | Deployment, Monitoring               | Secure Configuration Tools, Access Management Solutions    |
| LLM08:2025 Vector and Embedding Weaknesses | Training, Post-Deployment            | Bias Detection Tools, Secure Storage Solutions for Vectors |
| LLM09:2025 Misinformation                 | Training, Post-Deployment            | Cross-Verification Tools, Retrieval-Augmented Generation   |
| LLM10:2025 Unbounded Consumption          | Deployment, Monitoring               | Rate Limiting Tools, Load Balancing Solutions              |

---

This enhanced mapping of OWASP Top 10 for LLM Apps 2025 integrates each vulnerability with relevant lifecycle stages, ethical implications, practical tools, and stakeholder concerns, aligning with NIST AI RMF 1.0 standards to promote safe, scalable, and trustworthy AI applications.

**Next Steps**:
- Implement and prioritize mitigation strategies based on the identified risk level of each vulnerability.
- Use automated monitoring tools to ensure continuous compliance.
- Engage with AI security and ethics communities to refine practices.

**Further Reading**:
- [NIST AI RMF 1.0 (AI 100-1)](https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-development)
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org)


