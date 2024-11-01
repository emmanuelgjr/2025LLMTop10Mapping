# OWASP Top 10 for LLM Applications 2025 Mapped to CIS Controls

This repo maps the [**OWASP Top 10 for LLM Applications 2025**](https://genai.owasp.org/) vulnerabilities to the relevant CIS Controls. The goal is to help organizations better understand the security measures required to mitigate risks associated with LLM (Large Language Model) applications. The CIS Controls framework alignment offers organizations the ability to strengthen their security posture and adopt a structured approach to mitigating LLM-related vulnerabilities.

| Vulnerability | Risk Level | Description | CIS Controls | Mitigation Techniques |
| ------------- | ---------- | ----------- | ------------ | --------------------- |
| LLM01:2025 - Prompt Injection | High | Altering the behaviour or output of LLMs through crafted inputs | CIS Control 3: Data Protection, CIS Control 4: Secure Configuration of Enterprise Assets and Software, CIS Control 8: Audit Log Management | Input validation, secure configuration, logging |
| LLM02:2025 - Sensitive Information Disclosure | High | Unintentional exposure of sensitive information through LLM outputs | CIS Control 3: Data Protection, CIS Control 4: Secure Configuration, CIS Control 9: Email and Web Browser Protections | Data masking, access control, secure communication channels |
| LLM03:2025 - Supply Chain Vulnerabilities | Medium | Dependency on third-party components leading to risks like hijacking | CIS Control 2: Inventory and Control of Software Assets, CIS Control 5: Account Management, CIS Control 7: Continuous Vulnerability Management | Inventory management, access control, vulnerability assessments |
| LLM04:2025 - Data and Model Poisoning | High | Feeding malicious data into an LLM's training set, corrupting its behaviour | CIS Control 7: Continuous Vulnerability Management, CIS Control 13: Network Monitoring and Defense, CIS Control 18: Penetration Testing | Data integrity validation, network monitoring, adversarial testing |
| LLM05:2025 - Insecure Output Handling | Medium | Generating harmful content, leading to exploitation or abuse | CIS Control 3: Data Protection, CIS Control 8: Audit Log Management, CIS Control 16: Application Software Security | Output filtering, secure coding practices, logging |
| LLM06:2025 - Excessive Agency | Medium | LLMs have too much autonomy, leading to unauthorized actions | CIS Control 5: Account Management, CIS Control 11: Secure Configuration for Network Devices, CIS Control 17: Incident Response Management | Least privilege principles, restricted connectivity, incident response protocols |
| LLM07:2025 - System Prompt Leakage | Medium | Exposing system prompts or configuration details, leading to breaches | CIS Control 4: Secure Configuration, CIS Control 10: Malware Defenses, CIS Control 8: Audit Log Management | Concealment of prompts, malware defences, logging access attempts |
| LLM08:2025 - Vector and Embedding Weaknesses | Medium | Misuse of vectors and embeddings to manipulate LLM outputs or processes | CIS Control 16: Application Software Security, CIS Control 7: Continuous Vulnerability Management, CIS Control 3: Data Protection | Secure embedding techniques, vulnerability assessments, encryption |
| LLM09:2025 - Misinformation | High | Generating or propagating false information, leading to harmful decisions | CIS Control 13: Network Monitoring and Defense, CIS Control 17: Security Awareness and Skills Training, CIS Control 7: Continuous Vulnerability Management | Network monitoring, user training, misinformation detection |
| LLM10:2025 - Unbounded Consumption | Medium | Resource exhaustion caused by unbounded processing or interactions | CIS Control 4: Secure Configuration, CIS Control 5: Account Management, CIS Control 13: Network Monitoring and Defense | Resource constraints, role-based access control, network usage monitoring |


---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)

### Description
Prompt injection involves altering the behaviour or output of LLMs through crafted inputs. These vulnerabilities can bypass safety mechanisms and lead to unauthorized actions.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Implement data protection techniques to prevent the exposure of sensitive data through prompts.
  - Use input validation and output filtering to maintain data integrity.
- **CIS Control 4: Secure Configuration of Enterprise Assets and Software**
  - Configure LLMs securely to restrict access to only authorized inputs and outputs, reducing the impact of prompt injection.
- **CIS Control 8: Audit Log Management**
  - Maintain logs of all inputs, outputs, and alterations to monitor prompt injections and potential breaches.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)

### Description
This vulnerability involves the unintentional exposure of sensitive information like PII, financial data, or proprietary algorithms through LLM outputs.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Implement data masking and sanitization to prevent sensitive data from being included in LLM outputs.
- **CIS Control 4: Secure Configuration**
  - Configure LLMs to enforce strict access control and limit data retrieval to authorized users.
- **CIS Control 9: Email and Web Browser Protections**
  - Use secure communication channels and prevent exposure through external sources.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)

### Description
LLMs depend on third-party components, making them susceptible to supply chain risks such as dependency hijacking or backdoor injection.

### Relevant CIS Controls
- **CIS Control 2: Inventory and Control of Software Assets**
  - Regularly update the inventory of all software components used by LLMs to detect unauthorized changes.
- **CIS Control 5: Account Management**
  - Implement access control measures for supply chain components, ensuring only authorized access.
- **CIS Control 7: Continuous Vulnerability Management**
  - Conduct regular vulnerability assessments on third-party components used in LLMs.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)

### Description
Data poisoning involves feeding malicious data into an LLM's training set, potentially corrupting its behaviour.

### Relevant CIS Controls
- **CIS Control 7: Continuous Vulnerability Management**
  - Regularly assess the data sources and validate the integrity of training data.
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network traffic to detect and prevent unauthorized data manipulation attempts.
- **CIS Control 18: Penetration Testing**
  - Simulate adversarial attacks to identify and mitigate poisoning vulnerabilities.

---

## [LLM05:2025 - Insecure Output Handling](https://genai.owasp.org/)

### Description
Insecure output handling can cause LLMs to generate harmful content, leading to potential exploitation or abuse.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Use output filtering techniques to ensure responses are secure and do not expose sensitive data.
- **CIS Control 8: Audit Log Management**
  - Log all outputs to trace any unauthorized disclosure or harmful generation.
- **CIS Control 16: Application Software Security**
  - Implement secure coding practices to prevent code injection or unsafe execution through outputs.

---

## [LLM06:2025 - Excessive Agency](https://genai.owasp.org/)

### Description
Excessive agency refers to situations where LLMs have too much autonomy, potentially leading to unauthorized actions.

### Relevant CIS Controls
- **CIS Control 5: Account Management**
  - Apply least privilege principles to restrict LLM capabilities to necessary functions.
- **CIS Control 11: Secure Configuration for Network Devices**
  - Limit the connectivity of LLMs to reduce the risk of excessive actions.
- **CIS Control 17: Incident Response Management**
  - Establish protocols to respond to incidents caused by LLMs' unauthorized actions.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)

### Description
This vulnerability involves exposing system prompts or configuration details, leading to potential security breaches.

### Relevant CIS Controls
- **CIS Control 4: Secure Configuration**
  - Conceal system prompts to prevent attackers from gaining insights into internal configurations.
- **CIS Control 10: Malware Defenses**
  - Protect system files from unauthorized access to prevent prompt leakage.
- **CIS Control 8: Audit Log Management**
  - Log access to system prompts and configurations to detect unauthorized attempts.

---

## [LLM08:2025 - Vector and Embedding Weaknesses](https://genai.owasp.org/)

### Description
These weaknesses involve the misuse of vectors and embeddings to manipulate LLM outputs or internal processes.

### Relevant CIS Controls
- **CIS Control 16: Application Software Security**
  - Secure embedding techniques and implement controls to prevent vector-based manipulations.
- **CIS Control 7: Continuous Vulnerability Management**
  - Regularly assess vector spaces for vulnerabilities and anomalies.
- **CIS Control 3: Data Protection**
  - Ensure vector representations are encrypted and secured.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)

### Description
Misinformation occurs when LLMs generate or propagate false information, potentially leading to harmful decisions.

### Relevant CIS Controls
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network traffic for the dissemination of misinformation.
- **CIS Control 17: Security Awareness and Skills Training**
  - Educate users about misinformation risks and detection methods.
- **CIS Control 7: Continuous Vulnerability Management**
  - Continuously assess outputs to detect and correct misinformation.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

### Description
This vulnerability involves resource exhaustion caused by unbounded processing or interactions with LLMs.

### Relevant CIS Controls
- **CIS Control 4: Secure Configuration**
  - Implement resource constraints to prevent unbounded consumption.
- **CIS Control 5: Account Management**
  - Use role-based access control to limit user interactions that could lead to resource exhaustion.
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network usage and traffic to detect excessive consumption.


---

This mapping helps organizations align their AI application security strategies with the CIS Controls framework, promoting robust defence against LLM-related vulnerabilities. These controls when implemented allow organizations to effectively mitigate the unique risks associated with LLMs, fostering secure and trustworthy AI deployment.

## Further Reading
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org)
- [CIS Controls](https://www.cisecurity.org/controls)
- [AI and Machine Learning Security Guide](https://www.cisecurity.org/white-papers) 

For more resources and in-depth training on LLM application security, refer to the OWASP and CIS websites.
