# OWASP Top 10 for LLM Applications Mapped to SAMM

This repo maps the vulnerabilities described in the [OWASP Top 10 for Large Language Model Applications 2025](https://genai.owasp.org) to the [Software Assurance Maturity Model (SAMM)](https://owaspsamm.org/) framework, helping organizations assess, improve, and implement secure software development practices.


### 1. [LLM01:2025 Prompt Injection](https://genai.owasp.org)

**Description**: Prompt injection vulnerabilities occur when user inputs manipulate the LLM’s behaviour in unintended ways. This can lead to disclosure of sensitive information, unauthorized access, or critical decision manipulation.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Define clear prompt processing requirements to mitigate manipulation risks.
  - **Design**:
    - **Threat Assessment**: Include prompt injection scenarios in threat modelling to understand and predict potential prompt-based attacks.
  - **Implementation**:
    - **Secure Build**: Implement secure prompt handling code that validates and filters inputs.
  - **Verification**:
    - **Security Testing**: Conduct adversarial testing, including simulated prompt injection attacks, to validate resilience against input manipulation.
  - **Operations**:
    - **Environment Hardening**: Implement runtime safeguards to prevent prompt alterations and unauthorized command executions.

### 2. [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org)

**Description**: This vulnerability involves LLMs inadvertently revealing personal, proprietary, or confidential information due to flawed prompt handling or model design.

**SAMM Mapping**:
  - **Governance**:
    - **Compliance & Policy**: Establish data protection and privacy compliance policies to prevent sensitive information disclosure.
  - **Design**:
    - **Security Architecture**: Design models with data minimization principles, using anonymization and masking techniques.
  - **Implementation**:
    - **Secure Build**: Ensure sensitive data is excluded from model training and restrict data input handling to necessary contexts.
  - **Verification**:
    - **Security Testing**: Perform static and dynamic analysis to detect potential leaks of sensitive information.
  - **Operations**:
    - **Incident Management**: Implement processes to identify and respond to incidents of unintended sensitive data disclosure.

### 3. [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org)

**Description**: LLMs can be compromised via supply chain risks, such as malicious third-party libraries or poisoned datasets.

**SAMM Mapping**:
  - **Governance**:
    - **Compliance & Policy**: Establish policies that enforce third-party security assessments and supply chain integrity.
  - **Design**:
    - **Security Architecture**: Incorporate secure components, validating sources and dependencies of datasets and model libraries.
  - **Implementation**:
    - **External Dependencies Management**: Track and verify all third-party components used in LLM development.
  - **Verification**:
    - **Security Testing**: Conduct integrity checks on datasets and libraries before use in training or deployment.
  - **Operations**:
    - **Operational Monitoring**: Monitor for signs of supply chain compromise, such as unusual behaviour patterns in LLM outputs.

### 4. [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org)

**Description**: Data and model poisoning involves adversaries introducing malicious data to manipulate model training or outputs.

**SAMM Mapping**:
  - **Governance**:
    - **Compliance & Policy**: Include poisoning attack prevention in data handling policies.
  - **Design**:
    - **Security Architecture**: Implement strategies for data validation and anomaly detection to prevent poisoning.
  - **Implementation**:
    - **Secure Build**: Integrate data filtering mechanisms to detect and block suspicious data inputs.
  - **Verification**:
    - **Security Testing**: Use adversarial testing to simulate poisoning attempts and validate model integrity.
  - **Operations**:
    - **Environment Hardening**: Regularly update and retrain models to reduce the impact of poisoning over time.

### 5. [LLM05:2025 Insecure Output Handling](https://genai.owasp.org)

**Description**: Insecure handling of LLM outputs can lead to the generation of harmful, biased, or unauthorized content.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Define clear requirements for secure output handling and content filtering.
  - **Design**:
    - **Threat Assessment**: Analyze potential risks associated with different output scenarios.
  - **Implementation**:
    - **Secure Build**: Implement content filtering to ensure outputs comply with safety and ethical guidelines.
  - **Verification**:
    - **Security Testing**: Validate output filtering by testing for bias, offensive content, or other harmful results.
  - **Operations**:
    - **Incident Management**: Establish processes to address issues arising from insecure output handling.

### 6. [LLM06:2025 Excessive Agency](https://genai.owasp.org)

**Description**: LLMs may exhibit excessive autonomy, executing tasks without proper oversight, leading to unintended consequences.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Define boundaries for model capabilities and limitations.
  - **Design**:
    - **Security Architecture**: Ensure that LLMs operate within predefined scopes of functionality.
  - **Implementation**:
    - **Access Controls**: Implement controls that restrict the level of autonomy granted to LLMs.
  - **Verification**:
    - **Security Testing**: Test for unintended behaviours resulting from excessive model agency.
  - **Operations**:
    - **Operational Monitoring**: Continuously monitor LLM operations to prevent unauthorized actions.

### 7. [LLM07:2025 System Prompt Leakage](https://genai.owasp.org)

**Description**: System prompt leakage can expose sensitive information about the model's initial configuration or operating parameters.

**SAMM Mapping**:
  - **Governance**:
    - **Compliance & Policy**: Establish policies to secure system prompts against unauthorized access.
  - **Design**:
    - **Security Architecture**: Isolate and encrypt system prompts to prevent exposure.
  - **Implementation**:
    - **Secure Build**: Ensure that system prompts are hidden and inaccessible to users.
  - **Verification**:
    - **Security Testing**: Test for potential system prompt leaks during interactions.
  - **Operations**:
    - **Environment Hardening**: Implement measures to protect system prompts during deployment and operation.

### 8. [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org)

**Description**: Weaknesses in vector representation can lead to adversarial manipulation of LLMs.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Include vector security in data processing policies.
  - **Design**:
    - **Security Architecture**: Implement robust vector normalization and filtering.
  - **Implementation**:
    - **Secure Build**: Validate vector inputs and embeddings to prevent malicious manipulation.
  - **Verification**:
    - **Security Testing**: Perform tests to identify vulnerabilities in vector processing.
  - **Operations**:
    - **Operational Monitoring**: Monitor vectors for abnormal or adversarial patterns.

### 9. [LLM09:2025 Misinformation](https://genai.owasp.org)

**Description**: LLMs can produce inaccurate or misleading information that may have significant consequences.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Include misinformation detection and mitigation in policies.
  - **Design**:
    - **Security Architecture**: Implement content validation mechanisms.
  - **Implementation**:
    - **Output Control**: Validate model outputs for accuracy and trustworthiness.
  - **Verification**:
    - **Security Testing**: Conduct fact-checking tests on model outputs.
  - **Operations**:
    - **User Education**: Inform users about potential misinformation risks and provide guidance.

### 10. [LLM10:2025 Unbounded Consumption](https://genai.owasp.org)

**Description**: This vulnerability refers to excessive resource consumption by LLMs, potentially causing denial-of-service conditions.

**SAMM Mapping**:
  - **Governance**:
    - **Security Requirements**: Define limits for resource usage and consumption.
  - **Design**:
    - **Security Architecture**: Implement safeguards like rate limiting and timeout mechanisms.
  - **Implementation**:
    - **Resource Management**: Monitor and limit resource consumption at runtime.
  - **Verification**:
    - **Security Testing**: Test for excessive resource consumption scenarios.
  - **Operations**:
    - **Operational Monitoring**: Continuously monitor resource usage to prevent unbounded consumption.



It is crucial for stakeholders across governance, design, implementation, verification, and operational phases to continuously collaborate and ensure the responsible development and deployment of LLM technologies.

