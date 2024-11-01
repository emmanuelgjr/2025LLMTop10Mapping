# OWASP Top 10 for LLM Applications 2025 Mapped to BSIMM

This repo objective is to enhance LLM application security by mapping OWASP Top 10 for LLM Apps 2025 vulnerabilities to the [**Building Security In Maturity Model (BSIMM)**](https://www.blackduck.com/services/security-program/bsimm-maturity-model.html) framework.



| Vulnerability                            | BSIMM Categories                             | Description                                                                                       | Mitigation Strategies                                    | Resources                                                                                           |
|------------------------------------------|----------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| **LLM01:2025 Prompt Injection**          | SM1.1, SM2.3, ST3.3                         | Malicious prompts can alter LLM behavior.                                                         | Use prompt validation and filtering techniques.         | [Prompt Injection Attack Mitigations](https://genai.owasp.org)                                      |
| **LLM02:2025 Sensitive Information Disclosure** | CR1.2, SM1.3, ST3.4                   | LLMs may inadvertently expose PII or proprietary data.                                            | Redact sensitive data before LLM input.                 | [OWASP API Security Best Practices](https://owasp.org/API-Security/)                                |
| **LLM03:2025 Supply Chain Risks**        | AM2.2, AM3.3, SM2.4                         | Third-party components introduce risks to LLMs.                                                   | Assess and monitor dependencies.                        | [NIST AI Risk Management Framework](https://nvlpubs.nist.gov/nistpubs/ai/)                          |
| **LLM04:2025 Data and Model Poisoning**  | AM3.1, ST3.1, CR2.2                         | Malicious data can degrade model integrity.                                                       | Validate training data sources.                         | [MITRE ATLAS Techniques for LLM Poisoning](https://atlas.mitre.org)                                 |
| **LLM05:2025 Insecure Output Handling**  | ST3.2, SE2.2, AM1.3                         | Poor output handling may expose users to unintended content.                                      | Apply strict output validation.                         | [NIST AI Evaluation Techniques](https://nvlpubs.nist.gov/nistpubs/ai/)                              |
| **LLM06:2025 Excessive Agency**          | SM3.1, ST1.1, ST3.3                         | LLMs might perform unauthorized actions or exhibit autonomy.                                      | Establish strict behavioral controls for LLMs.          | [LLM Governance Best Practices](https://genai.owasp.org)                                            |
| **LLM07:2025 System Prompt Leakage**     | SE1.1, ST1.3, AM2.3                         | Internal prompts may expose sensitive information.                                                | Secure prompt configurations.                           | [Securing Prompts in AI Systems](https://genai.owasp.org)                                           |
| **LLM08:2025 Vector and Embedding Weaknesses** | ST1.4, SE3.1, AM1.1                  | Manipulating vectors can exploit LLM vulnerabilities.                                             | Enforce secure vector handling.                         | [Vector Security in AI](https://arxiv.org/abs/2307.00691)                                           |
| **LLM09:2025 Misinformation**            | CR2.1, SE3.2, SM2.2                         | LLMs may generate misinformation, affecting credibility.                                          | Monitor and filter outputs for misinformation.          | [Mitigating AI Misinformation](https://genai.owasp.org)                                             |
| **LLM10:2025 Unbounded Consumption**     | AM2.1, SE2.1, CR1.1                         | LLMs may consume excessive resources, leading to DoS conditions.                                  | Implement resource consumption limits.                  | [AI System Resource Limiting](https://genai.owasp.org)                                              |

---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org)

- **Description:** Malicious prompts can alter LLM behaviour, resulting in unauthorized data access or unintended operations.

- **BSIMM Mapping:**
  - **SM1.1:** Include LLM models in software inventory for monitoring.
  - **SM2.3:** Review prompt filtering and validation security features.
  - **ST3.3:** Add LLM prompt validation techniques, like semantic filtering, to control libraries.

  - **Mitigation**: Use prompt validation and filtering techniques to prevent malicious alterations to LLM behavior. Ensure that only approved prompts are processed and that unauthorized commands are blocked.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org)
- **Description:** LLMs may inadvertently expose PII or proprietary data.
- **BSIMM Mapping:**
  - **CR1.2:** Extend data classification to LLM inputs and outputs.
  - **SM1.3:** Establish guidelines for redacting sensitive data.
  - **ST3.4:** Ensure secure LLM deployment configurations prevent data leaks.
- **Resources:** [OWASP API Security Best Practices](https://owasp.org/API-Security/)

  - **Mitigation**: Redact sensitive data before input into the LLM. Implement strict access controls to limit exposure of Personally Identifiable Information (PII) and proprietary data.

---

## [LLM03:2025 Supply Chain Risks](https://genai.owasp.org)
- **Description:** LLMs depend on third-party components, introducing supply chain risks.
- **BSIMM Mapping:**
  - **AM2.2:** Assess third-party software dependencies in LLMs.
  - **AM3.3:** Include LLM data suppliers in security assessments.
  - **SM2.4:** Test third-party integrations for vulnerabilities.
- **Resources:** [NIST AI Risk Management Framework](https://nvlpubs.nist.gov/nistpubs/ai/)

  - **Mitigation**: Assess and monitor third-party dependencies regularly. Include security reviews in the supply chain and evaluate all third-party data sources and components used by the LLM.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org)
- **Description:** Malicious data can poison training, degrading model integrity.
- **BSIMM Mapping:**
  - **AM3.1:** Prepare response programs for LLM model poisoning.
  - **ST3.1:** Include model poisoning in LLM threat models.
  - **CR2.2:** Incorporate model integrity risks in security analyses.
- **Resources:** [MITRE ATLAS Techniques for LLM Poisoning](https://atlas.mitre.org)

  - **Mitigation**: Validate and sanitize all training data sources. Perform adversarial testing to identify potential poisoning risks and implement controls to detect and prevent malicious data.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org)
- **Description:** Poor handling of LLM outputs can generate harmful or unintended content.
- **BSIMM Mapping:**
  - **ST3.2:** Analyze output handling risks in LLM architecture.
  - **SE2.2:** Ensure consistent output validation and content filtering.
  - **AM1.3:** Track compliance of LLM outputs with security policies.
- **Resources:** [NIST AI Evaluation Techniques](https://nvlpubs.nist.gov/nistpubs/ai/)

  - **Mitigation**: Apply strict output validation, including content filtering and secure formatting. Ensure outputs do not inadvertently expose or generate harmful or unintended content.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org)
- **Description:** LLMs may exhibit unexpected autonomy, performing unauthorized actions.
- **BSIMM Mapping:**
  - **SM3.1:** Develop expertise in governing LLM behaviour limits.
  - **ST1.1:** Assess risks of excessive LLM autonomy.
  - **ST3.3:** Implement strict controls to enforce LLM behaviour constraints.
- **Resources:** [LLM Governance Best Practices](https://genai.owasp.org/resource/llm-applications-cybersecurity-and-governance-checklist-english/)

  - **Mitigation**: Establish behavioural constraints and enforce access controls to prevent unauthorized or excessive actions by the LLM, limiting the autonomy of LLMs to intended functions.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org)
- **Description:** LLMs may expose internal prompts, revealing sensitive information.
- **BSIMM Mapping:**
  - **SE1.1:** Prevent prompt leakage through secure coding standards.
  - **ST1.3:** Secure configurations to avoid internal prompt exposure.
  - **AM2.3:** Analyze prompt handling for potential exposure.
- **Resources:** [Securing Prompts in AI Systems](https://genai.owasp.org)

  - **Mitigation**: Secure system prompts by configuring access restrictions and securing internal prompt structures. Avoid exposing internal system configurations or sensitive prompts to users.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org)
- **Description:** Manipulating vectors and embeddings can exploit LLM vulnerabilities.
- **BSIMM Mapping:**
  - **ST1.4:** Assess security assumptions related to vector manipulation.
  - **SE3.1:** Apply secure design principles to embeddings.
  - **AM1.1:** Monitor vector manipulation in threat intelligence.
- **Resources:** [Vector Security in AI](https://arxiv.org/abs/2307.00691)

  - **Mitigation**: Enforce secure handling practices for vectors and embeddings. Monitor for manipulation risks and validate that vector operations meet security standards.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org)
- **Description:** LLMs may generate misinformation, affecting system credibility.
- **BSIMM Mapping:**
  - **CR2.1:** Simulate misinformation attacks for resilience testing.
  - **SE3.2:** Test for misinformation vulnerabilities.
  - **SM2.2:** Integrate mitigation strategies for misinformation risks.
- **Resources:** [Mitigating AI Misinformation](https://genai.owasp.org)

  - **Mitigation**: Monitor outputs for misinformation, integrate fact-checking processes, and apply filters to ensure the accuracy and reliability of generated information.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org)
- **Description:** LLMs can be triggered to consume excessive resources, causing DoS conditions.
- **BSIMM Mapping:**
  - **AM2.1:** Enforce resource limits to prevent DoS in LLMs.
  - **SE2.1:** Add security checks for unbounded consumption vulnerabilities.
  - **CR1.1:** Limit resource consumption with access controls.
- **Resources:** [AI System Resource Limiting](https://genai.owasp.org)

  - **Mitigation**: Implement resource consumption limits to prevent Denial-of-Service (DoS) conditions, ensuring that the LLM application does not exhaust system resources.

---

The OWASP Top 10 for LLM Applications mapped to the BSIMM framework provides a structured approach to improving the security of large language models. It takes great effort to understand the specific vulnerabilities unique to LLMs and apply established security practices, this will allow organizations to better safeguard their AI systems against emerging threats. Continuous assessment, testing, and monitoring are essential to address evolving risks and ensure robust security measures are in place.

