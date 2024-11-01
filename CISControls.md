# OWASP Top 10 for LLM Applications 2025 Mapped to CIS Controls

This repo maps the [**OWASP Top 10 for LLM Applications 2025**](https://genai.owasp.org/) vulnerabilities to the relevant [**Centre for Internet Security - CIS Controls**](https://www.cisecurity.org/controls). The goal is to help organizations better understand the security measures required to mitigate risks associated with LLM (Large Language Model) applications. The CIS Controls framework alignment offers organizations the ability to strengthen their security posture and adopt a structured approach to mitigating LLM-related vulnerabilities.

```html
<table>
  <thead>
    <tr>
      <th style="white-space: nowrap;">Vulnerability</th>
      <th>Risk Level</th>
      <th>Description</th>
      <th>CIS Control</th>
      <th>Mitigation Techniques</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="white-space: nowrap;">LLM01:2025 - Prompt Injection</td>
      <td>High</td>
      <td>Altering the behavior or output of LLMs through crafted inputs</td>
      <td>CIS Control 3: Data Protection</td>
      <td>Implement input validation to prevent malicious input that can alter LLM behavior.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 4: Secure Configuration of Enterprise Assets and Software</td>
      <td>Secure LLM configurations to restrict inputs and outputs to authorized users.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 8: Audit Log Management</td>
      <td>Maintain logs of inputs and outputs to detect prompt injection attempts.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;">LLM02:2025 - Sensitive Information Disclosure</td>
      <td>High</td>
      <td>Unintentional exposure of sensitive information through LLM outputs</td>
      <td>CIS Control 3: Data Protection</td>
      <td>Implement data masking and sanitization techniques to prevent the exposure of sensitive information.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 4: Secure Configuration</td>
      <td>Enforce strict access control to limit data retrieval to authorized users.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 9: Email and Web Browser Protections</td>
      <td>Use secure communication channels to prevent data leakage.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;">LLM03:2025 - Supply Chain Vulnerabilities</td>
      <td>Medium</td>
      <td>Dependency on third-party components leading to risks like hijacking</td>
      <td>CIS Control 2: Inventory and Control of Software Assets</td>
      <td>Maintain an updated inventory of all software components used by LLMs.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 5: Account Management</td>
      <td>Implement access control for third-party components, allowing only authorized access.</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"></td>
      <td></td>
      <td></td>
      <td>CIS Control 7: Continuous Vulnerability Management</td>
      <td>Conduct regular vulnerability assessments on all supply chain components.</td>
    </tr>
    <!-- Additional rows for each vulnerability -->
  </tbody>
</table>
```


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
