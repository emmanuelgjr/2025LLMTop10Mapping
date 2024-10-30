# OWASP Top 10 for LLM Applications 2025 Mapped to BSIMM

This repo objective is to enhance LLM application security by mapping OWASP Top 10 for LLM Apps 2025 vulnerabilities to the BSIMM framework.

## LLM01:2025 Prompt Injection
- **Description:** Malicious prompts can alter LLM behavior, resulting in unauthorized data access or unintended operations.
- **BSIMM Mapping:**
  - **SM1.1:** Include LLM models in software inventory for monitoring.
  - **SM2.3:** Review prompt filtering and validation security features.
  - **ST3.3:** Add LLM prompt validation techniques, like semantic filtering, to control libraries.
- **Resources:** [Prompt Injection Attack Mitigations](https://genai.owasp.org)

## LLM02:2025 Sensitive Information Disclosure
- **Description:** LLMs may inadvertently expose PII or proprietary data.
- **BSIMM Mapping:**
  - **CR1.2:** Extend data classification to LLM inputs and outputs.
  - **SM1.3:** Establish guidelines for redacting sensitive data.
  - **ST3.4:** Ensure secure LLM deployment configurations prevent data leaks.
- **Resources:** [OWASP API Security Best Practices](https://owasp.org/API-Security/)

## LLM03:2025 Supply Chain Risks
- **Description:** LLMs depend on third-party components, introducing supply chain risks.
- **BSIMM Mapping:**
  - **AM2.2:** Assess third-party software dependencies in LLMs.
  - **AM3.3:** Include LLM data suppliers in security assessments.
  - **SM2.4:** Test third-party integrations for vulnerabilities.
- **Resources:** [NIST AI Risk Management Framework](https://nvlpubs.nist.gov/nistpubs/ai/)

## LLM04:2025 Data and Model Poisoning
- **Description:** Malicious data can poison training, degrading model integrity.
- **BSIMM Mapping:**
  - **AM3.1:** Prepare response programs for LLM model poisoning.
  - **ST3.1:** Include model poisoning in LLM threat models.
  - **CR2.2:** Incorporate model integrity risks in security analyses.
- **Resources:** [MITRE ATLAS Techniques for LLM Poisoning](https://atlas.mitre.org)

## LLM05:2025 Insecure Output Handling
- **Description:** Poor handling of LLM outputs can generate harmful or unintended content.
- **BSIMM Mapping:**
  - **ST3.2:** Analyze output handling risks in LLM architecture.
  - **SE2.2:** Ensure consistent output validation and content filtering.
  - **AM1.3:** Track compliance of LLM outputs with security policies.
- **Resources:** [NIST AI Evaluation Techniques](https://nvlpubs.nist.gov/nistpubs/ai/)

## LLM06:2025 Excessive Agency
- **Description:** LLMs may exhibit unexpected autonomy, performing unauthorized actions.
- **BSIMM Mapping:**
  - **SM3.1:** Develop expertise in governing LLM behavior limits.
  - **ST1.1:** Assess risks of excessive LLM autonomy.
  - **ST3.3:** Implement strict controls to enforce LLM behavior constraints.
- **Resources:** [LLM Governance Best Practices](https://genai.owasp.org)

## LLM07:2025 System Prompt Leakage
- **Description:** LLMs may expose internal prompts, revealing sensitive information.
- **BSIMM Mapping:**
  - **SE1.1:** Prevent prompt leakage through secure coding standards.
  - **ST1.3:** Secure configurations to avoid internal prompt exposure.
  - **AM2.3:** Analyze prompt handling for potential exposure.
- **Resources:** [Securing Prompts in AI Systems](https://genai.owasp.org)

## LLM08:2025 Vector and Embedding Weaknesses
- **Description:** Manipulating vectors and embeddings can exploit LLM vulnerabilities.
- **BSIMM Mapping:**
  - **ST1.4:** Assess security assumptions related to vector manipulation.
  - **SE3.1:** Apply secure design principles to embeddings.
  - **AM1.1:** Monitor vector manipulation in threat intelligence.
- **Resources:** [Vector Security in AI](https://arxiv.org/abs/2307.00691)

## LLM09:2025 Misinformation
- **Description:** LLMs may generate misinformation, affecting system credibility.
- **BSIMM Mapping:**
  - **CR2.1:** Simulate misinformation attacks for resilience testing.
  - **SE3.2:** Test for misinformation vulnerabilities.
  - **SM2.2:** Integrate mitigation strategies for misinformation risks.
- **Resources:** [Mitigating AI Misinformation](https://genai.owasp.org)

## LLM10:2025 Unbounded Consumption
- **Description:** LLMs can be triggered to consume excessive resources, causing DoS conditions.
- **BSIMM Mapping:**
  - **AM2.1:** Enforce resource limits to prevent DoS in LLMs.
  - **SE2.1:** Add security checks for unbounded consumption vulnerabilities.
  - **CR1.1:** Limit resource consumption with access controls.
- **Resources:** [AI System Resource Limiting](https://genai.owasp.org)

The OWASP Top 10 for LLM Applications, when mapped to the BSIMM framework, provides a structured approach to improving the security of large language models. By understanding the specific vulnerabilities unique to LLMs and applying established security practices, organizations can better safeguard their AI systems against emerging threats. Continuous assessment, testing, and monitoring are essential to address evolving risks and ensure robust security measures are in place.

