# OWASP Top 10 for LLM Applications: Mapping to CIS Controls

## Executive Summary

This document maps the *OWASP Top 10 for LLM Applications 2025* vulnerabilities to the relevant CIS Controls. The goal is to help organizations better understand the security measures required to mitigate risks associated with LLM (Large Language Model) applications. By aligning with the CIS Controls framework, organizations can strengthen their security posture and adopt a structured approach to mitigating LLM-related vulnerabilities.

---

## LLM01:2025 - Prompt Injection: Mapped CIS Controls

### Description
Prompt injection involves altering the behavior or output of LLMs through crafted inputs. These vulnerabilities can bypass safety mechanisms and lead to unauthorized actions.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Implement data protection techniques to prevent the exposure of sensitive data through prompts.
  - Use input validation and output filtering to maintain data integrity.
- **CIS Control 4: Secure Configuration of Enterprise Assets and Software**
  - Configure LLMs securely to restrict access to only authorized inputs and outputs, reducing the impact of prompt injection.
- **CIS Control 8: Audit Log Management**
  - Maintain logs of all inputs, outputs, and alterations to monitor prompt injections and potential breaches.

[Learn more about CIS Control 3](https://www.cisecurity.org/controls/data-protection) | [OWASP Top 10 for LLMs:2025 Prompt Injection](https://genai.owasp.org)

## LLM02:2025 - Sensitive Information Disclosure: Mapped CIS Controls

### Description
This vulnerability involves the unintentional exposure of sensitive information like PII, financial data, or proprietary algorithms through LLM outputs.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Implement data masking and sanitization to prevent sensitive data from being included in LLM outputs.
- **CIS Control 4: Secure Configuration**
  - Configure LLMs to enforce strict access control and limit data retrieval to authorized users.
- **CIS Control 9: Email and Web Browser Protections**
  - Use secure communication channels and prevent exposure through external sources.

[Learn more about CIS Control 4](https://www.cisecurity.org/controls/secure-configuration) | [OWASP Top 10 for LLMs:2025 Sensitive Information Disclosure](https://genai.owasp.org)

## LLM03:2025 - Supply Chain Vulnerabilities: Mapped CIS Controls

### Description
LLMs depend on third-party components, making them susceptible to supply chain risks such as dependency hijacking or backdoor injection.

### Relevant CIS Controls
- **CIS Control 2: Inventory and Control of Software Assets**
  - Regularly update the inventory of all software components used by LLMs to detect unauthorized changes.
- **CIS Control 5: Account Management**
  - Implement access control measures for supply chain components, ensuring only authorized access.
- **CIS Control 7: Continuous Vulnerability Management**
  - Conduct regular vulnerability assessments on third-party components used in LLMs.

[Learn more about CIS Control 2](https://www.cisecurity.org/controls/inventory-and-control-of-software-assets) | [OWASP Top 10 for LLMs:2025 Supply Chain Risks](https://genai.owasp.org)

## LLM04:2025 - Data and Model Poisoning: Mapped CIS Controls

### Description
Data poisoning involves feeding malicious data into an LLM's training set, potentially corrupting its behavior.

### Relevant CIS Controls
- **CIS Control 7: Continuous Vulnerability Management**
  - Regularly assess the data sources and validate the integrity of training data.
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network traffic to detect and prevent unauthorized data manipulation attempts.
- **CIS Control 18: Penetration Testing**
  - Simulate adversarial attacks to identify and mitigate poisoning vulnerabilities.

[Learn more about CIS Control 7](https://www.cisecurity.org/controls/continuous-vulnerability-management) | [OWASP Top 10 for LLMs:2025 Data and Model Poisoning](https://genai.owasp.org)

## LLM05:2025 - Insecure Output Handling: Mapped CIS Controls

### Description
Insecure output handling can cause LLMs to generate harmful content, leading to potential exploitation or abuse.

### Relevant CIS Controls
- **CIS Control 3: Data Protection**
  - Use output filtering techniques to ensure responses are secure and do not expose sensitive data.
- **CIS Control 8: Audit Log Management**
  - Log all outputs to trace any unauthorized disclosure or harmful generation.
- **CIS Control 16: Application Software Security**
  - Implement secure coding practices to prevent code injection or unsafe execution through outputs.

[Learn more about CIS Control 16](https://www.cisecurity.org/controls/application-software-security) | [OWASP Top 10 for LLMs:2025 Insecure Output Handling](https://genai.owasp.org)

## LLM06:2025 - Excessive Agency: Mapped CIS Controls

### Description
Excessive agency refers to situations where LLMs have too much autonomy, potentially leading to unauthorized actions.

### Relevant CIS Controls
- **CIS Control 5: Account Management**
  - Apply least privilege principles to restrict LLM capabilities to necessary functions.
- **CIS Control 11: Secure Configuration for Network Devices**
  - Limit the connectivity of LLMs to reduce the risk of excessive actions.
- **CIS Control 17: Incident Response Management**
  - Establish protocols to respond to incidents caused by LLMs' unauthorized actions.

[Learn more about CIS Control 11](https://www.cisecurity.org/controls/secure-configuration-for-network-devices) | [OWASP Top 10 for LLMs:2025 Excessive Agency](https://genai.owasp.org)

## LLM07:2025 - System Prompt Leakage: Mapped CIS Controls

### Description
This vulnerability involves exposing system prompts or configuration details, leading to potential security breaches.

### Relevant CIS Controls
- **CIS Control 4: Secure Configuration**
  - Conceal system prompts to prevent attackers from gaining insights into internal configurations.
- **CIS Control 10: Malware Defenses**
  - Protect system files from unauthorized access to prevent prompt leakage.
- **CIS Control 8: Audit Log Management**
  - Log access to system prompts and configurations to detect unauthorized attempts.

[Learn more about CIS Control 10](https://www.cisecurity.org/controls/malware-defenses) | [OWASP Top 10 for LLMs:2025 System Prompt Leakage](https://genai.owasp.org)

## LLM08:2025 - Vector and Embedding Weaknesses: Mapped CIS Controls

### Description
These weaknesses involve the misuse of vectors and embeddings to manipulate LLM outputs or internal processes.

### Relevant CIS Controls
- **CIS Control 16: Application Software Security**
  - Secure embedding techniques and implement controls to prevent vector-based manipulations.
- **CIS Control 7: Continuous Vulnerability Management**
  - Regularly assess vector spaces for vulnerabilities and anomalies.
- **CIS Control 3: Data Protection**
  - Ensure vector representations are encrypted and secured.

[Learn more about CIS Control 16](https://www.cisecurity.org/controls/application-software-security) | [OWASP Top 10 for LLMs:2025 Vector Weaknesses](https://genai.owasp.org)

## LLM09:2025 - Misinformation: Mapped CIS Controls

### Description
Misinformation occurs when LLMs generate or propagate false information, potentially leading to harmful decisions.

### Relevant CIS Controls
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network traffic for the dissemination of misinformation.
- **CIS Control 17: Security Awareness and Skills Training**
  - Educate users about misinformation risks and detection methods.
- **CIS Control 7: Continuous Vulnerability Management**
  - Continuously assess outputs to detect and correct misinformation.

[Learn more about CIS Control 13](https://www.cisecurity.org/controls/network-monitoring-and-defense) | [OWASP Top 10 for LLMs:2025 Misinformation](https://genai.owasp.org)

## LLM10:2025 - Unbounded Consumption: Mapped CIS Controls

### Description
This vulnerability involves resource exhaustion caused by unbounded processing or interactions with LLMs.

### Relevant CIS Controls
- **CIS Control 4: Secure Configuration**
  - Implement resource constraints to prevent unbounded consumption.
- **CIS Control 5: Account Management**
  - Use role-based access control to limit user interactions that could lead to resource exhaustion.
- **CIS Control 13: Network Monitoring and Defense**
  - Monitor network usage and traffic to detect excessive consumption.

[Learn more about CIS Control 4](https://www.cisecurity.org/controls/secure-configuration) | [OWASP Top 10 for LLMs:2025 Unbounded Consumption](https://genai.owasp.org)

---

## Conclusion
This mapping helps organizations align their AI application security strategies with the CIS Controls framework, promoting robust defense against LLM-related vulnerabilities. By implementing these controls, organizations can effectively mitigate the unique risks associated with LLMs, fostering secure and trustworthy AI deployment.

## Further Reading
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org)
- [CIS Controls](https://www.cisecurity.org/controls)
- [AI and Machine Learning Security Guide](https://www.cisecurity.org/white-papers) 

For more resources and in-depth training on LLM application security, refer to the OWASP and CIS websites.
