# OWASP Top 10 for LLM Applications 2025 Mapped to STRIDE

This repo presents a comprehensive mapping of each vulnerability in the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to the [STRIDE threat model](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats#stride-model). STRIDE categorizes threats into six types: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privileges.



| Vulnerability                       | STRIDE Categories                                |
|-------------------------------------|--------------------------------------------------|
| LLM01:2025 Prompt Injection    | Spoofing, Tampering, Elevation of Privileges     |
| LLM02:2025 Sensitive Information Disclosure | Information Disclosure, Tampering       |
| LLM03:2025 Supply Chain Risks   | Tampering, Denial of Service                     |
| LLM04:2025 Data and Model Poisoning | Tampering, Denial of Service                 |
| LLM05:2025 Insecure Output Handling | Information Disclosure, Tampering           |
| LLM06:2025 Excessive Agency     | Elevation of Privileges, Denial of Service       |
| LLM07:2025 System Prompt Leakage| Information Disclosure                           |
| LLM08:2025 Vector and Embedding Weaknesses | Tampering, Information Disclosure        |
| LLM09:2025 Misinformation       | Information Disclosure, Tampering                |
| LLM10:2025 Unbounded Consumption | Denial of Service                               |


---

### LLM01:25 Prompt Injection

**Description:** User inputs manipulate LLM behaviour, bypassing safeguards, generating harmful content, or gaining unauthorized access.

**STRIDE Categories:**
  - **Spoofing:** Manipulation of identity in responses or behaviour.
  - **Tampering:** Altering input prompts to change responses.
  - **Elevation of Privileges:** Gaining unauthorized access through crafted prompts.
- **Mitigation:** Constrain model behaviour, validate outputs, enforce privilege control, and implement input filtering.
- **More Info:** [Prompt Injection in AI Systems](https://arxiv.org/abs/2302.12173)


### LLM02:2025 Sensitive Information Disclosure

**Description:** Exposure of sensitive data (e.g., PII, financial information) through model outputs.

**STRIDE Categories:**
  - **Information Disclosure:** Unintentional data leakage.
  - **Tampering:** Model inversion to extract confidential information.
- **Mitigation:** Data sanitization, robust input validation, access controls, and differential privacy.
- **More Info:** [OWASP API Security: Security Misconfiguration](https://owasp.org/API-Security/editions/2023/en/0xa8-security-misconfiguration/)


### LLM03:2025 Supply Chain Risks

**Description:** Vulnerabilities in third-party components, libraries, or datasets used by LLMs.

**STRIDE Categories:**
  - **Tampering:** Manipulation of supply chain elements.
  - **Denial of Service:** Malicious components causing system unavailability.
- **Mitigation:** Use signed components, monitor continuously, and conduct vendor risk assessments.
- **More Info:** [Software Supply Chain Security](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)


### LLM04:2025 Data and Model Poisoning

**Description:** Corruption of training data or models to influence outputs.

**STRIDE Categories:**
  - **Tampering:** Malicious data modification.
  - **Denial of Service:** Overwhelming the model with poisoned data.
- **Mitigation:** Use federated learning, adversarial training, and data validation.
- **More Info:** [Adversarial Machine Learning](https://atlas.mitre.org/techniques/AML.T0051.001)


### LLM05:2025 Insecure Output Handling

**Description:** Poor handling of outputs leads to misuse, such as exposing URLs or unsafe code execution.

**STRIDE Categories:**
  - **Information Disclosure:** Exposing unintended information.
  - **Tampering:** Manipulating responses users rely on.
- **Mitigation:** Define strict output formats, enforce context adherence, and filter outputs.
- **More Info:** [Output Handling in LLMs](https://research.kudelskisecurity.com/2023/05/25/reducing-the-impact-of-prompt-injection-attacks-through-design/)


### LLM06:2025 Excessive Agency

**Description:** Models autonomously execute privileged actions without sufficient checks.

**STRIDE Categories:**
  - **Elevation of Privileges:** Unchecked execution of actions beyond permissions.
  - **Denial of Service:** Disruptions from autonomous actions.
- **Mitigation:** Implement human-in-the-loop controls, privilege management, and restrict model actions.
- **More Info:** [LLM Autonomous Risks](https://aivillage.org/large%20language%20models/threat-modeling-llm/)


### LLM07:2025 System Prompt Leakage

**Description:** Exposure of system prompts or internal instructions, compromising security.

**STRIDE Categories:**
  - **Information Disclosure:** Revealing internal prompts.
- **Mitigation:** Mask sensitive system instructions and restrict prompt access.
- **More Info:** [Protecting System Prompts](https://arxiv.org/abs/2306.05499)


### LLM08:2025 Vector and Embedding Weaknesses

**Description:** Manipulation of embedding vectors to alter model responses or infer sensitive data.

**STRIDE Categories:**
  - **Tampering:** Modifying vectors to influence outcomes.
  - **Information Disclosure:** Exploiting embeddings to reveal model knowledge.
- **Mitigation:** Secure embedding techniques and vector sanitization.
- **More Info:** [Embedding Security](https://ieeexplore.ieee.org/document/10579515)


### LLM09:2025 Misinformation

**Description:** Model outputs contain inaccuracies, unsupported claims, or unsafe code.

**STRIDE Categories:**
  - **Information Disclosure:** Dissemination of false information.
  - **Tampering:** Generating misleading content.
- **Mitigation:** Use retrieval-augmented generation, cross-verification, and human oversight.
- **More Info:** [Misinformation in AI Systems](https://arxiv.org/abs/2307.00691)


### LLM10:2025 Unbounded Consumption

**Description:** Excessive resource consumption, causing denial of service or performance issues.

**STRIDE Categories:**
  - **Denial of Service:** Overconsumption of resources.
- **Mitigation:** Enforce rate limits, monitor usage, and apply resource constraints.
- **More Info:** [Resource Management in AI](https://arxiv.org/abs/2407.07403)

---

This mapping aligns each vulnerability from the OWASP Top 10 for LLM Applications with relevant STRIDE categories, providing insights into potential risks and mitigation strategies. For more detailed information, refer to the resources linked under each vulnerability.

