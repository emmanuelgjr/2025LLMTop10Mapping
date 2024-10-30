# OWASP Top 10 for Large Language Model Applications 2025 Mapped to MITRE ATLAS

This repo presents a detailed mapping of the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to the [MITRE ATLAS](https://atlas.mitre.org) framework. It aims to provide security practitioners with a comprehensive understanding of vulnerabilities, associated threats, and recommended mitigations in Large Language Model (LLM) applications, aligning efforts across both OWASP and MITRE frameworks for a robust AI security posture.

## Table of Contents
1. [LLM01:2025 - Prompt Injection](https://genai.owasp.org)
2. [LLM02:2025 - Sensitive Information Disclosure](https://genai.owasp.org)
3. [LLM03:2025 - Supply Chain Vulnerabilities](https://genai.owasp.org)
4. [LLM04:2025 - Data and Model Poisoning](https://genai.owasp.org)
5. [LLM05:2025 - Insecure Output Handling](https://genai.owasp.org)
6. [LLM06:2025 - Excessive Agency](https://genai.owasp.org)
7. [LLM07:2025 - System Prompt Leakage](https://genai.owasp.org)
8. [LLM08:2025 - Vector and Embedding Weaknesses](https://genai.owasp.org)
9. [LLM09:2025 - Misinformation](https://genai.owasp.org)
10. [LLM10:2025 - Unbounded Consumption](https://genai.owasp.org)

---

### LLM01:2025 - Prompt Injection
**Description:** Prompt injection attacks exploit the LLM’s input interpretation by introducing malicious instructions into the model’s prompt. This can lead to modified model behaviour, execution of unauthorized actions, or bypassing of security measures. Prompt injection can be **direct** (manipulating user input fields) or **indirect** (modifying underlying system prompts).

- **MITRE ATLAS Mapping:** 
  - [AML.T0051.000 - Direct Prompt Injection](https://atlas.mitre.org/techniques/AML.T0051.000): Direct manipulation of prompts during user interactions.
  - [AML.T0051.001 - Indirect Prompt Injection](https://atlas.mitre.org/techniques/AML.T0051.001): Modification of prompts indirectly, such as through back-end processes.
  - [AML.T0054 - LLM Jailbreak Injection](https://atlas.mitre.org/techniques/AML.T0054): Circumvention of safety measures via prompt-based exploits.

**Mitigation Strategies:**
- Implement strict input validation and sanitization protocols.
- Deploy adversarial testing techniques to identify prompt vulnerabilities.
- Enforce constraints on model responses and interactions.

---

### LLM02:2025 - Sensitive Information Disclosure
**Description:** LLMs may inadvertently expose sensitive data like Personally Identifiable Information (PII), financial details, proprietary code, or algorithms during output generation. This can occur due to training data leakage, overexposed embeddings, or improperly sanitized responses.

- **MITRE ATLAS Mapping:** 
  - [AML.T0021 - Data Leakage](https://atlas.mitre.org/techniques/AML.T0021): Unintended exposure of sensitive data from models.
  - [AML.T0030 - Information Disclosure](https://atlas.mitre.org/techniques/AML.T0030): Release of confidential information through model outputs.

**Mitigation Strategies:**
- Use data sanitization tools to redact sensitive elements from output.
- Employ differential privacy techniques during training and inference.
- Implement role-based access controls to restrict sensitive data access.

---

### LLM03:2025 - Supply Chain Vulnerabilities
**Description:** Vulnerabilities in the LLM supply chain, such as compromised model weights, data poisoning, or third-party dependencies, can lead to corrupted outputs, unintended behaviours, or security breaches.

- **MITRE ATLAS Mapping:** 
  - [AML.T0056 - Adversarial Model Manipulation](https://atlas.mitre.org/techniques/AML.T0056): Malicious alterations of model components during the supply chain process.
  - [AML.T0048 - Model Contamination](https://atlas.mitre.org/techniques/AML.T0048): Insertion of adversarial data or backdoors during model development.

**Mitigation Strategies:**
- Implement model provenance checks and digital signatures to verify authenticity.
- Use federated learning to decentralize training processes, reducing exposure.
- Conduct code integrity checks and secure third-party dependencies.

---

### LLM04:2025 - Data and Model Poisoning
**Description:** Data poisoning involves introducing malicious inputs into the training dataset, which can skew outputs or introduce harmful behaviours. Model poisoning modifies model weights directly, leading to biased results, safety compromises, or unintentional actions.

- **MITRE ATLAS Mapping:** 
  - [AML.T0032 - Data Poisoning](https://atlas.mitre.org/techniques/AML.T0032): Insertion of harmful data into the training pipeline.
  - [AML.T0027 - Model Inversion](https://atlas.mitre.org/techniques/AML.T0027): Leveraging model outputs to reverse-engineer sensitive data.

**Mitigation Strategies:**
- Implement robust data validation and filtering during the training process.
- Use adversarial training techniques to harden models against poisoning.
- Monitor data pipelines continuously for abnormal inputs or patterns.

---

### LLM05:2025 - Insecure Output Handling
**Description:** Improper handling of model outputs can result in vulnerabilities such as command injection, cross-site scripting (XSS), or other unintended actions. This can occur due to a lack of output sanitization, insufficient encoding, or insecure content rendering.

- **MITRE ATLAS Mapping:** 
  - [AML.T0037 - Output Manipulation](https://atlas.mitre.org/techniques/AML.T0037): Exploitation of improperly handled model outputs.

**Mitigation Strategies:**
- Use output sanitization techniques to remove potential harmful elements.
- Implement content filtering and secure rendering practices.
- Enforce secure coding guidelines to prevent code injection via model outputs.

---

### LLM06:2025 - Excessive Agency
**Description:** Excessive agency arises when an LLM is granted too much control over critical processes or decision-making, leading to risks like unauthorized command execution, privilege escalation, or unintended actions with severe impacts.

- **MITRE ATLAS Mapping:** 
  - [AML.T0015 - LLM Capability Escalation](https://atlas.mitre.org/techniques/AML.T0015): Escalation of model capabilities beyond intended scopes.

**Mitigation Strategies:**
- Implement least-privilege access controls for model operations.
- Use human-in-the-loop (HITL) verification for high-risk decisions.
- Limit autonomous execution of sensitive commands or processes.

---

### LLM07:2025 - System Prompt Leakage
**Description:** Leakage of system prompts can expose internal instructions, configurations, or preambles, leading to compromised model behaviour or unauthorized access to sensitive configurations.

- **MITRE ATLAS Mapping:** 
  - [AML.T0041 - Configuration Exposure](https://atlas.mitre.org/techniques/AML.T0041): Exposure of internal configurations or system settings.

**Mitigation Strategies:**
- Secure system prompts through access restrictions and encrypted storage.
- Use tokenization to protect sensitive parts of system-level prompts.
- Monitor prompt usage to detect potential leaks.

---

### LLM08:2025 - Vector and Embedding Weaknesses
**Description:** Weaknesses in vectors and embeddings can lead to adversarial manipulation, where attackers modify vectors to alter model outputs or behaviours. Embeddings may also expose sensitive patterns if improperly handled.

- **MITRE ATLAS Mapping:** 
  - [AML.T0063 - Embedding Manipulation](https://atlas.mitre.org/techniques/AML.T0063): Alteration of embeddings to influence model behavior.

**Mitigation Strategies:**
- Implement vector validation and regularization techniques.
- Use adversarial testing frameworks to detect embedding vulnerabilities.
- Secure embedding generation with access controls and encryption.

---

### LLM09:2025 - Misinformation
**Description:** Misinformation involves generating incorrect or misleading information that affects decision-making, spreads disinformation, or creates confusion.

- **MITRE ATLAS Mapping:** 
  - [AML.T0045 - Disinformation](https://atlas.mitre.org/techniques/AML.T0045): Creation of false or misleading information by the model.

**Mitigation Strategies:**
- Use retrieval-augmented generation (RAG) to enhance factual accuracy.
- Implement cross-verification techniques and human review for critical outputs.
- Monitor model performance for consistent accuracy and reliability.

---

### LLM10:2025 - Unbounded Consumption
**Description:** LLMs can be exploited to consume excessive computational or memory resources, leading to denial-of-service (DoS) conditions, resource exhaustion, or other availability issues.

- **MITRE ATLAS Mapping:** 
  - [AML.T0025 - Resource Exhaustion](https://atlas.mitre.org/techniques/AML.T0025): Overconsumption of resources by the model.

**Mitigation Strategies:**
- Implement rate limiting and quota enforcement on API calls and model access.
- Use activity monitoring tools to identify abnormal resource usage.
- Design models to handle resource constraints efficiently.

---

## Conclusion
This mapping provides a critical alignment between the **OWASP Top 10 for LLM Applications 2025** and the **MITRE ATLAS** framework, supporting AI practitioners in identifying, categorizing, and mitigating security risks within LLM deployments. The combined insights from these frameworks offer a more holistic approach to managing AI security, facilitating threat-informed defence strategies that prioritize proactive measures, continuous monitoring, and robust risk management. By understanding these vulnerabilities and adopting the recommended defences, organizations can enhance the security of their AI systems, reduce potential attack surfaces, and ensure compliance with evolving security standards.

---
