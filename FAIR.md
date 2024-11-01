# OWASP Top 10 for LLM Applications 2025 Mapped to FAIR

This repo maps the vulnerabilities identified in the [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org) to the [FAIR (Factors for the Analysis of Information Risk) framework](https://www.fairinstitute.org/). The FAIR model helps analyze information security risks through a structured approach to understanding the potential impact and likelihood of risks related to Large Language Models (LLMs).

## FAIR Model Overview
The FAIR model evaluates risk through two main components:
- **Loss Event Frequency (LEF)**: Likelihood of a risk materializing.
- **Loss Magnitude (LM)**: Potential impact if the risk occurs.

These components help contextualize LLM vulnerabilities by examining their nature, controls, and consequences.


# Vulnerabilities and FAIR Mapping Table

| **Vulnerability**                | **FAIR Mapping**                                                                                                                                                                  |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| LLM01:2025 Prompt Injection  | **TEF**: High - Prompt injections are easy to attempt. <br> **Vulnerability**: High susceptibility due to reliance on external inputs. <br> **Loss Factors**: Productivity loss, response cost. |
| LLM02:2025 Sensitive Information Disclosure | **Control Strength**: Moderate to Weak - Depending on safeguards. <br> **Potential Loss**: Confidentiality breach, fines, and penalties.                                         |
| LLM03:2025 Supply Chain Vulnerabilities     | **Threat Capability**: High - Exploitation of dependencies. <br> **Potential Impact**: Reputation damage, productivity loss.                                                     |
| LLM04:2025 Data and Model Poisoning         | **Control Strength**: Weak - Hard to detect and mitigate. <br> **Loss Factors**: Competitive disadvantage, recovery costs.                                                       |
| LLM05:2025 Insecure Output Handling         | **TEF**: Moderate - Lack of rigorous output filters. <br> **Potential Impact**: Confidentiality breach, operational disruption.                                                   |
| LLM06:2025 Excessive Agency                 | **Vulnerability**: High - Unintended actions by autonomous LLMs. <br> **Potential Impact**: Operational risk, safety risk.                                                       |
| LLM07:2025 System Prompt Leakage            | **Control Strength**: Moderate - Strong configurations, but bypassable. <br> **Loss Factors**: Confidentiality breach, legal consequences.                                      |
| LLM08:2025 Vector and Embedding Weaknesses  | **TEF**: Moderate - Requires specific knowledge. <br> **Potential Impact**: Operational disruption, security breach.                                                              |
| LLM09:2025 Misinformation Generation        | **Control Strength**: Weak - Difficult to detect. <br> **Potential Loss**: Reputation damage, compliance issues.                                                                 |
| LLM10:2025 Unbounded Consumption            | **Threat Capability**: High - If resource limits are not enforced. <br> **Potential Impact**: Service downtime, operational costs.                                              |



## LLM01:2025 Prompt Injection
- **Description**: Manipulation of model behaviour via crafted inputs.
- **FAIR Mapping**:
  - **Threat Event Frequency (TEF)**: High - Prompt injections are relatively easy to attempt, increasing attack frequency.
  - **Vulnerability**: LLMs are highly susceptible due to their reliance on external inputs.
  - **Primary Loss Factors**:
    - **Productivity Loss**: Incorrect outputs or compromised decision-making.
    - **Response Cost**: Resources needed for incident response and correction.
- **References**:
  - [Prompt Injection Attack Analysis](https://arxiv.org/abs/2302.12173)


## LLM02:2025 Sensitive Information Disclosure
- **Description**: Unintended exposure of personal or sensitive data.
- **FAIR Mapping**:
  - **Control Strength**: Moderate to Weak - Depending on safeguards like data sanitization and encryption.
  - **Potential Loss**:
    - **Confidentiality Breach**: Exposure of PII, proprietary data, or credentials.
    - **Fines and Penalties**: Possible legal consequences under regulations like GDPR or CCPA.
- **References**:
  - [Privacy Risks in LLMs](https://arxiv.org/abs/2307.00691)

## LLM03:2025 Supply Chain Vulnerabilities
- **Description**: Exploits stemming from third-party components in LLM integrations.
- **FAIR Mapping**:
  - **Threat Capability**: High - Attackers can exploit dependencies or libraries, leading to model compromise.
  - **Potential Impact**:
    - **Reputation Damage**: Publicized breaches can harm credibility.
    - **Productivity Loss**: Service disruptions during vulnerability patching.
- **References**:
  - [Software Supply Chain Risks](https://atlas.mitre.org/techniques/AML.T0054)


## LLM04:2025 Data and Model Poisoning
- **Description**: Introducing malicious data to manipulate model outputs.
- **FAIR Mapping**:
  - **Control Strength**: Weak - Poisoning attacks are hard to detect and mitigate.
  - **Primary Loss Factors**:
    - **Competitive Disadvantage**: Manipulated outputs can lead to flawed decisions.
    - **Recovery Costs**: Time and effort to retrain the model.
- **References**:
  - [Adversarial Machine Learning Attacks](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)

## LLM05:2025 Insecure Output Handling
- **Description**: Inadequate handling of generated responses, leading to data leakage or other unintended outcomes.
- **FAIR Mapping**:
  - **Threat Event Frequency**: Moderate - If output filters are not rigorously applied.
  - **Potential Impact**:
    - **Confidentiality Breach**: Unintentional data disclosure through responses.
    - **Operational Disruption**: Erroneous or harmful outputs can affect workflows.
- **References**:
  - [LLM Output Risks](https://research.kudelskisecurity.com/2023/05/25/reducing-the-impact-of-prompt-injection-attacks-through-design)


## LLM06:2025 Excessive Agency
- **Description**: Models autonomously making decisions beyond intended use.
- **FAIR Mapping**:
  - **Vulnerability**: High - LLMs designed for autonomous operations may execute unintended actions.
  - **Potential Impact**:
    - **Operational Risk**: Erroneous transactions or decisions.
    - **Safety Risk**: Potential harm to physical systems (e.g., industrial automation).
- **References**:
  - [AI Decision-Making Risks](https://aivillage.org/large%20language%20models/threat-modeling-llm/)

## LLM07:2025 System Prompt Leakage
- **Description**: Exposure of internal prompts that reveal system architecture or logic.
- **FAIR Mapping**:
  - **Control Strength**: Moderate - Strong configurations may prevent access, but are bypassable.
  - **Loss Factors**:
    - **Confidentiality Breach**: Attackers gain insight into system functioning.
    - **Legal Consequences**: Violation of data handling regulations.
- **References**:
  - [System Prompt Leakage Analysis](https://embracethered.com/blog/posts/2023/chatgpt-cross-plugin-request-forgery-and-prompt-injection)


## LLM08:2025 Vector and Embedding Weaknesses
- **Description**: Exploiting vulnerabilities in the embeddings used in LLMs.
- **FAIR Mapping**:
  - **Threat Event Frequency**: Moderate - Attackers need specific knowledge to exploit embeddings.
  - **Potential Impact**:
    - **Operational Disruption**: Manipulation of embeddings can affect model behaviour and outputs.
    - **Security Breach**: Embedded vectors could reveal sensitive data patterns.
- **References**:
  - [Adversarial Attacks on Embeddings](https://arxiv.org/abs/2407.07403)

## LLM09:2025 Misinformation Generation
- **Description**: LLMs generating and spreading false or misleading information.
- **FAIR Mapping**:
  - **Control Strength**: Weak - Detection of misinformation is still challenging.
  - **Potential Loss**:
    - **Reputation Damage**: Loss of trust due to false outputs.
    - **Compliance Issues**: Misinformation in regulated industries can lead to legal consequences.
- **References**:
  - [Misinformation in AI](https://arxiv.org/abs/2306.05499)


## LLM10:2025 Unbounded Consumption
- **Description**: Overuse of system resources or API calls leading to denial of service.
- **FAIR Mapping**:
  - **Threat Capability**: High - If resource limits are not enforced.
  - **Potential Impact**:
    - **Service Downtime**: Unintended outages or degraded service.
    - **Operational Costs**: Increased infrastructure expenses.
- **References**:
  - [Resource Management in AI Systems](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2023.pdf)

Mapping the OWASP Top 10 vulnerabilities for LLM applications to the FAIR framework is essential for understanding and mitigating risks in AI systems. The FAIR Framework applied to organizations can assess the frequency and magnitude of potential losses, enabling them to prioritize security measures and make informed decisions to minimize vulnerabilities. This mapping also provides a structured approach to identifying key risk factors, supporting a more resilient and secure implementation of LLM technologies.
