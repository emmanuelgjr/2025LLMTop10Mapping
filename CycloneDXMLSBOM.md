# OWASP Top 10 for LLM Applications 2025 Mapped to CycloneDX ML SBOM

This repo mapped vulnerabilities from the [OWASP Top 10 for Large Language Model Applications 2025](https://genai.owasp.org) to the [CycloneDX Machine Learning Software Bill of Materials (ML SBOM)](https://cyclonedx.org/capabilities/mlbom/). The purpose is to enhance the security, transparency, and integrity of LLM-based systems through a structured ML SBOM.

| **Vulnerabilities**                                | **Risk Rating** | **CycloneDX ML SBOM**                                                                                                                                                         | **Suggested Tools**                             |
|------------------------------------------------|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| LLM01:2025 - Prompt Injection                  | High            | **Component Metadata**: Track prompt handlers and filters <br> **Data Sources & Inputs**: Validate user inputs <br> **Security Testing**: Include injection test cases       | SecML, TextAttack                              |
| LLM02:2025 - Sensitive Information Disclosure  | High            | **Data Lineage**: Document sensitive data and access controls <br> **Privacy Controls**: List masking or differential privacy <br> **Access Restrictions**: Access configs  | Amazon Macie, BigID                            |
| LLM03:2025 - Supply Chain Risks                | Medium          | **Dependency Inventory**: List external dependencies and libraries <br> **Provenance Verification**: Use cryptographic signatures <br> **Component Risks**: Identify issues | OWASP Dependency-Check, Snyk                   |
| LLM04:2025 - Data and Model Poisoning          | High            | **Training Data Records**: Document data sources <br> **Model Integrity**: Validate against poisoning attempts <br> **Testing Artifacts**: Include adversarial tests         | IBM Adversarial Robustness Toolbox, SecML      |
| LLM05:2025 - Insecure Output Handling          | Medium          | **Output Validation**: Detail output sanitization routines <br> **Response Filtering**: Filter for unsafe responses <br> **Security Testing**: Test for safe responses       | Veracode, OWASP ZAP                            |
| LLM06:2025 - Excessive Agency                  | High            | **Component Permissions**: Track permissions <br> **Access Controls**: Apply least-privilege principles <br> **Audit Mechanisms**: Add RBAC and access logs                 | AWS IAM Access Analyzer, Okta                  |
| LLM07:2025 - System Prompt Leakage             | Medium          | **Prompt Handling**: Mask and restrict prompt access <br> **Access Controls**: Limit prompt exposure <br> **Testing**: Test for prompt leakage scenarios                    | Veracode, Burp Suite                           |
| LLM08:2025 - Vector and Embedding Weaknesses   | Medium          | **Embedding Mechanisms**: Track vectorization methods <br> **Adversarial Testing**: Document anomaly detection <br> **Integrity Monitoring**: Monitor embedding behavior    | CleverHans, IBM Adversarial Robustness Toolbox |
| LLM09:2025 - Misinformation                    | High            | **Output Verification**: Implement cross-verification and review <br> **Filtering**: Detect and filter misinformation <br> **Oversight**: Include human review              | Google Fact Check API, MisinfoMe               |
| LLM10:2025 - Unbounded Consumption             | Medium          | **Resource Limits**: Document memory and processing limits <br> **Performance Monitoring**: Track resource use <br> **Rate-Limiting**: Configure limits to prevent DoS      | Prometheus, Grafana                            |


---

## 1. [LLM01:2025 - Prompt Injection](https://genai.owasp.org/)

> **Description**  
> **Prompt Injection** occurs when malicious user inputs manipulate the behaviour or output of an LLM in unexpected ways. Attackers can craft inputs that bypass filters, modify responses, or exploit weaknesses in prompt processing logic. This vulnerability can lead to unauthorized actions, the generation of harmful content, exposure of sensitive information, or biased decision-making.

### CycloneDX SBOM Mapping
- **Component Metadata**: Capture details of prompt handling components, including software versions, prompt templates, and input validation mechanisms.
- **Data Sources & Inputs**: Document the sources of inputs, including user, system, or third-party inputs, and specify input filtering and sanitization techniques.
- **Security Testing**: Include test cases for detecting prompt injection, ensuring coverage in both development and production environments.

### Mitigation Strategies
- Implement **robust data sanitization** and **validation** checks for all user inputs.
- Define **input handling configurations** in the SBOM, including filtering rules, test coverage, and sanitization routines.
- Use **contextual encoding** to ensure inputs are correctly processed without altering the prompt's intended behaviour.
- Integrate **testing tools** that simulate prompt injection attempts and document their results within the SBOM.

### Reference Links
- [MITRE ATLAS: LLM Prompt Injection - Direct](https://atlas.mitre.org/techniques/AML.T0051.000)
- [MITRE ATLAS: LLM Prompt Injection - Indirect](https://atlas.mitre.org/techniques/AML.T0051.001)
- [OWASP Cheat Sheet: Input Validation](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html)

---

## 2. [LLM02:2025 - Sensitive Information Disclosure](https://genai.owasp.org/)

> **Description**  
> **Sensitive Information Disclosure** occurs when Personally Identifiable Information (PII), financial data, proprietary information, or other sensitive details are unintentionally exposed through LLM responses. This can result from inadequate data handling, poor access controls, or flawed response generation logic.

### CycloneDX SBOM Mapping
- **Data Lineage**: Track the sources of sensitive data, specifying encryption methods, access controls, and data flow within the SBOM.
- **Privacy Controls**: Document mechanisms such as data masking, tokenization, or differential privacy, ensuring these are reflected in the SBOM.
- **Access Restrictions**: Include access control configurations for components interacting with sensitive data.

### Mitigation Strategies
- Implement **data classification** and **masking** techniques to prevent unintentional disclosure.
- Use **differential privacy** or **federated learning** to protect data at rest and during processing.
- Include **privacy compliance** measures and anonymization techniques in the SBOM to ensure adherence to privacy laws like GDPR or CCPA.
- Regularly review and update **encryption and decryption processes** to maintain confidentiality.

### Reference Links
- [OWASP API Security: Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)
- [NIST Privacy Framework](https://www.nist.gov/privacy-framework)

---

## 3. [LLM03:2025 - Supply Chain Risks](https://genai.owasp.org/)

> **Description**  
> **Supply Chain Risks** involve vulnerabilities introduced by third-party libraries, models, datasets, or dependencies used in LLM development. Malicious or compromised components in the supply chain can degrade system integrity, introduce backdoors, or expose sensitive data.

### CycloneDX SBOM Mapping
- **Dependency Inventory**: Maintain an accurate list of external dependencies, including libraries, models, datasets, and APIs.
- **Provenance Verification**: Include cryptographic signatures, hashes, or checksums for third-party components to verify their integrity.
- **Component Risks**: Identify potential risks associated with each dependency, such as known vulnerabilities or licensing issues.

### Mitigation Strategies
- Implement **automated tools** to detect outdated or vulnerable dependencies, ensuring the SBOM is kept up-to-date.
- Include **version control details** in the SBOM, with automated checks for dependency updates or replacements.
- Conduct **supplier risk assessments** and document the results in the SBOM, ensuring supply chain transparency.

### Reference Links
- [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)
- [NIST Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/projects/cyber-supply-chain-risk-management)

---

## 4. [LLM04:2025 - Data and Model Poisoning](https://genai.owasp.org/)

> **Description**  
> **Data and Model Poisoning** involves the manipulation of training data or fine-tuning processes to alter the behaviour of LLMs. Attackers may introduce biased data, erroneous labels, or malicious samples, leading to degraded model performance, biased outputs, or unintended actions.

### CycloneDX SBOM Mapping
- **Training Data Records**: Track training datasets and their sources, documenting preprocessing methods, validation checks, and provenance in the SBOM.
- **Model Integrity**: Document fine-tuning processes and validation procedures, specifying defences against poisoning attempts.
- **Testing Artifacts**: Include adversarial testing results in the SBOM, along with monitoring for anomalies in model outputs.

### Mitigation Strategies
- Use **adversarial testing** to identify and mitigate poisoning attempts during training and fine-tuning.
- Implement **data validation and cleansing** techniques to ensure the integrity and accuracy of training datasets.
- Incorporate **model validation checks** to detect anomalies or biases resulting from poisoned data.

### Reference Links
- [MITRE ATLAS: Adversarial Machine Learning](https://atlas.mitre.org/adversarial-ml/)
- [OWASP Testing Guide: Adversarial Machine Learning](https://owasp.org/www-project-testing-guide/)

---

Here's the continuation from **LLM05:2025** to **LLM10:2025**, maintaining the expanded structure for each entry and adhering to GitHub markdown best practices.

---

## 5. [LLM05:2025 - Insecure Output Handling](https://genai.owasp.org/)

> **Description**  
> **Insecure Output Handling** occurs when an LLM generates responses that inadvertently expose sensitive data, enable injection attacks, or deliver unsafe content. This may result from insufficient validation of outputs or a failure to properly sanitize responses before they reach the user.

### CycloneDX SBOM Mapping
- **Output Validation Mechanisms**: Document output validation routines and configurations, specifying sanitization methods and encoding techniques.
- **Response Filtering**: Include details of filtering systems designed to remove potentially unsafe outputs, and ensure they are tested and updated regularly.
- **Security Testing**: Add security test cases focused on output validation to identify potential leakage or malicious content generation.

### Mitigation Strategies
- Implement **output sanitization** and **contextual encoding** to ensure responses are safe and do not reveal sensitive information.
- Regularly update and document **response filters** and output validation logic in the SBOM, ensuring coverage of new potential attack vectors.
- Use **monitoring tools** to detect and flag anomalies in generated outputs, incorporating the results into the SBOM.

### Reference Links
- [OWASP Output Encoding Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Output_Encoding_Cheat_Sheet.html)
- [NIST Secure Software Development Framework (SSDF)](https://csrc.nist.gov/publications/detail/white-paper/2020/04/23/secure-software-development-framework-ssdf-final)

---

## 6. [LLM06:2025 - Excessive Agency](https://genai.owasp.org/)

> **Description**  
> **Excessive Agency** occurs when LLMs are granted more permissions or capabilities than necessary, potentially enabling unauthorized actions or escalating privileges. This can result from improper access controls, excessive permissions, or inadequate role-based restrictions.

### CycloneDX SBOM Mapping
- **Component Permissions**: Track and document the permissions of each LLM component, specifying which capabilities are allowed and restricting unnecessary permissions.
- **Access Controls**: Record the implementation of least-privilege principles, including user roles, permission levels, and access rules.
- **Audit Mechanisms**: Include audit logs and role-based access control (RBAC) configurations in the SBOM to ensure oversight of LLM actions.

### Mitigation Strategies
- Implement **least-privilege** and **zero-trust** principles to limit LLM access to only necessary resources.
- Use **role-based access controls (RBAC)** or **attribute-based access controls (ABAC)** to enforce strict permission boundaries, documented within the SBOM.
- Continuously review and update **permissions** to prevent privilege escalation, and incorporate access audit results into the SBOM.

### Reference Links
- [OWASP Top 10: Broken Access Control](https://owasp.org/Top10/A04_2021-Broken_Access_Control/)
- [NIST Special Publication 800-53: Access Control](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)

---

## 7. [LLM07:2025 - System Prompt Leakage](https://genai.owasp.org/)

> **Description**  
> **System Prompt Leakage** occurs when internal system prompts or configurations meant to guide LLM behaviour are inadvertently exposed through LLM outputs. This may reveal sensitive instructions, debugging prompts, or operational secrets that should remain hidden.

### CycloneDX SBOM Mapping
- **Prompt Handling Details**: Include system prompt metadata in the SBOM, specifying access restrictions, encoding methods, and masking techniques.
- **Access Controls for Prompts**: Document prompt storage locations, access restrictions, and sanitization methods to prevent leaks.
- **Testing Artifacts**: Integrate prompt exposure tests in the SBOM, ensuring consistent testing for prompt leakage risks.

### Mitigation Strategies
- Implement **prompt encoding** and **masking techniques** to obscure sensitive prompts, documenting these methods in the SBOM.
- Ensure **least-privilege access** to prompt configurations, reducing the risk of unauthorized access or exposure.
- Regularly review and audit **prompt-handling procedures** and configurations, incorporating findings into the SBOM.

### Reference Links
- [OWASP Security Logging and Monitoring Failures](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/)
- [NIST Guidelines for Managing Information Security](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-100.pdf)

---

## 8. [LLM08:2025 - Vector and Embedding Weaknesses](https://genai.owasp.org/)

> **Description**  
> **Vector and Embedding Weaknesses** involve vulnerabilities in the representation of data as vectors, which can be manipulated by adversaries to introduce biases or adversarial examples. These weaknesses may lead to incorrect model outputs, privacy leaks, or degraded system performance.

### CycloneDX SBOM Mapping
- **Embedding Mechanisms**: Document vectorization and embedding methods used within the LLM, specifying known vulnerabilities and their mitigations.
- **Adversarial Testing Results**: Include results from adversarial tests focused on embeddings, detailing detection algorithms and mitigation measures.
- **Anomaly Detection**: Integrate anomaly detection algorithms in the SBOM to monitor vector integrity and detect potential attacks.

### Mitigation Strategies
- Conduct **adversarial testing** on embeddings to identify potential weaknesses and mitigate their impact, documenting results in the SBOM.
- Use **robust vectorization methods** that are less susceptible to manipulation, and include these methods within the SBOM.
- Implement **monitoring tools** to detect anomalous vector behaviour, ensuring real-time response capabilities.

### Reference Links
- [OWASP Adversarial Machine Learning](https://owasp.org/www-community/Adversarial_Machine_Learning)
- [NIST Special Publication 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)

---

## 9. [LLM09:2025 - Misinformation](https://genai.owasp.org/)

> **Description**  
> **Misinformation** occurs when LLMs generate false, misleading, or harmful outputs, often due to flawed training data, biased models, or lack of verification mechanisms. This can degrade user trust and introduce risks of misinformation dissemination.

### CycloneDX SBOM Mapping
- **Output Validation Methods**: Document cross-verification methods, human oversight processes, and validation algorithms for output generation.
- **Misinformation Filtering**: Include components that detect and filter misinformation, specifying validation techniques in the SBOM.
- **Human Oversight**: Track human review procedures in the SBOM, ensuring critical outputs are verified before dissemination.

### Mitigation Strategies
- Implement **cross-verification methods** to ensure output accuracy and consistency, documenting these methods in the SBOM.
- Use **misinformation detection algorithms** to flag potentially false outputs, ensuring they are filtered or corrected before release.
- Incorporate **human review steps** into the output validation process, particularly for sensitive or high-impact outputs.

### Reference Links
- [OWASP Automated Threats: Adversarial AI](https://owasp.org/www-project-automated-threats-to-web-applications/)
- [NIST Artificial Intelligence Risk Management Framework (AI RMF)](https://www.nist.gov/ai)

---

## 10. [LLM10:2025 - Unbounded Consumption](https://genai.owasp.org/)

> **Description**  
> **Unbounded Consumption** refers to uncontrolled resource usage by LLMs, potentially leading to denial of service (DoS) attacks or severe performance degradation. This can occur due to improper rate-limiting, memory overflow, or excessive processing demands.

### CycloneDX SBOM Mapping
- **Resource Constraints**: Document memory limits, processing thresholds, and API rate-limiting configurations in the SBOM.
- **Performance Monitoring**: Include performance monitoring tools that track resource usage and trigger alerts when thresholds are exceeded.
- **Rate-Limiting Details**: Specify rate-limiting configurations in the SBOM to prevent DoS attacks and ensure resource efficiency.

### Mitigation Strategies
- Implement **rate-limiting controls** at both the API and model levels to prevent excessive resource consumption, documenting them in the SBOM.
- Use **resource management tools** to monitor and optimize memory, CPU, and storage usage, ensuring efficient model operation.
- Incorporate **scalability measures** to handle sudden surges in requests, preventing service interruptions and performance degradation.

### Reference Links
- [OWASP DoS Attack Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/DoS_Attack_Prevention_Cheat_Sheet.html)
- [NIST Secure Cloud Computing Framework](https://www.nist.gov/cloud-computing)

---

## Further Reading
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org)
- [CycloneDX Specification for SBOM](https://cyclonedx.org/specification/)
- [NIST AI Risk Management Framework](https://www.nist.gov/ai)
- [OWASP ML Security Cheat Sheet](https://owasp.org/www-project-machine-learning-security/)

---

This comprehensive mapping of the OWASP Top 10 for LLM Applications 2025 to the CycloneDX ML SBOM provides a structured approach to securing LLM deployments. Organizations incorporating SBOM principles can enhance transparency, traceability, and integrity across the entire lifecycle of LLM systems, from initial development to deployment and continuous monitoring. These mappings facilitate a proactive stance against evolving threats, helping to minimize risks, improve response times, and ensure compliance with regulatory requirements.

The adoption of a robust ML AI SBOM integrated with security best practices from the OWASP Top 10 for LLM Applications is not just a technical necessity but also a critical part of responsible AI deployment. As LLM technologies become increasingly central to various industries, it is essential to foster a culture of security, privacy, and accountability. This repo offers stakeholders the ability to establish a stronger security foundation for their AI systems, ensuring safer, more resilient, and trustworthy AI implementations that align with ethical standards and societal expectations.

