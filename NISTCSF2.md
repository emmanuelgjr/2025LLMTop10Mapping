# Mapping OWASP Top 10 for Large Language Model Applications to NIST Cybersecurity Framework (CSF) 2.0

This document provides a comprehensive mapping of each vulnerability from the OWASP Top 10 for LLM Applications to the corresponding categories, subcategories, and functions in the NIST Cybersecurity Framework (CSF) 2.0.

## Table of Contents

1. [Overview](#overview)
2. [Mapping OWASP Top 10 for LLM Applications to NIST CSF 2.0](#mapping)
   - [LLM01:2025 - Prompt Injection](#llm01-2025---prompt-injection)
   - [LLM02:2025 - Sensitive Information Disclosure](#llm02-2025---sensitive-information-disclosure)
   - [LLM03:2025 - Supply Chain Risks](#llm03-2025---supply-chain-risks)
   - [LLM04:2025 - Data and Model Poisoning](#llm04-2025---data-and-model-poisoning)
   - [LLM05:2025 - Insecure Output Handling](#llm05-2025---insecure-output-handling)
   - [LLM06:2025 - Excessive Agency](#llm06-2025---excessive-agency)
   - [LLM07:2025 - System Prompt Leakage](#llm07-2025---system-prompt-leakage)
   - [LLM08:2025 - Vector and Embedding Weaknesses](#llm08-2025---vector-and-embedding-weaknesses)
   - [LLM09:2025 - Misinformation](#llm09-2025---misinformation)
   - [LLM10:2025 - Unbounded Consumption](#llm10-2025---unbounded-consumption)
3. [Conclusion](#conclusion)

## Overview

The [OWASP Top 10 for LLM Applications](https://genai.owasp.org) is a guide designed to help developers, security teams, and stakeholders understand the security risks associated with deploying Large Language Models (LLMs). By mapping these vulnerabilities to the [NIST CSF 2.0](https://www.nist.gov/cyberframework), we aim to integrate these risks into a widely recognized security framework, facilitating better risk management and response.

## Mapping OWASP Top 10 for LLM Applications to NIST CSF 2.0 <a name="mapping"></a>

The following sections provide detailed mappings of each vulnerability from the OWASP Top 10 for LLM Applications (2025) to the appropriate functions, categories, and subcategories within NIST CSF 2.0.

### LLM01:2025 - Prompt Injection <a name="llm01-2025---prompt-injection"></a>

- **Description**: Prompt Injection occurs when user inputs manipulate the model's behavior in unintended ways, potentially leading to unauthorized access, content manipulation, or security breaches.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.AM-5**: Resources (including hardware, devices, data, and software) are prioritized based on their classification, criticality, and business value to ensure secure LLM deployment.
  - **Protect (PR)**:
    - **PR.AC-5**: Implement network integrity controls such as network segregation to limit unintended model interactions.
    - **PR.DS-1**: Protect data-at-rest to prevent malicious manipulation of prompt data.
  - **Detect (DE)**:
    - **DE.AE-5**: Aggregate and correlate event data from multiple sources to detect prompt injection attempts.
  - **Respond (RS)**:
    - **RS.AN-4**: Analyze incident data to assess the impact of prompt injection attacks on the organization.

[Learn more about Prompt Injection](https://genai.owasp.org)

### LLM02:2025 - Sensitive Information Disclosure <a name="llm02-2025---sensitive-information-disclosure"></a>

- **Description**: Unintentional disclosure of sensitive data through model outputs, including Personally Identifiable Information (PII), proprietary data, or confidential information.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.GV-3**: Establish governance processes that address risks associated with LLM-generated outputs.
  - **Protect (PR)**:
    - **PR.DS-3**: Manage assets formally throughout removal, transfers, and disposition to prevent accidental disclosure.
    - **PR.PT-1**: Implement security technologies to ensure system resilience against data leaks.
  - **Detect (DE)**:
    - **DE.CM-1**: Monitor network activity to detect potential data disclosure events.
  - **Respond (RS)**:
    - **RS.MI-2**: Mitigate incidents of sensitive information disclosure according to established procedures.

[Learn more about Sensitive Information Disclosure](https://genai.owasp.org)

### LLM03:2025 - Supply Chain Risks <a name="llm03-2025---supply-chain-risks"></a>

- **Description**: Risks arising from third-party components or dependencies in the model's supply chain, which could compromise integrity or introduce vulnerabilities.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.BE-5**: Address supply chain risk management processes to mitigate cyber risks from third-party dependencies.
  - **Protect (PR)**:
    - **PR.DS-6**: Use integrity checking mechanisms to verify the integrity of hardware and software in the supply chain.
  - **Detect (DE)**:
    - **DE.CM-7**: Monitor for unauthorized connections, devices, or software introduced through the supply chain.
  - **Respond (RS)**:
    - **RS.AN-5**: Establish processes to receive, analyze, and respond to supply chain threats.

[Learn more about Supply Chain Risks](https://genai.owasp.org)

### LLM04:2025 - Data and Model Poisoning <a name="llm04-2025---data-and-model-poisoning"></a>

- **Description**: Attacks that compromise data or models by injecting malicious inputs during training, leading to biased or manipulated outputs.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.RA-3**: Conduct risk assessments that include scenarios involving data or model poisoning.
  - **Protect (PR)**:
    - **PR.DS-8**: Maintain the integrity and confidentiality of data to prevent poisoning attacks.
  - **Detect (DE)**:
    - **DE.DP-3**: Analyze notifications from detection systems to ensure appropriate actions are taken.
  - **Respond (RS)**:
    - **RS.MI-3**: Mitigate newly identified vulnerabilities arising from data and model poisoning.

[Learn more about Data and Model Poisoning](https://genai.owasp.org)

### LLM05:2025 - Insecure Output Handling <a name="llm05-2025---insecure-output-handling"></a>

- **Description**: Improper handling of generated content that could lead to security issues, such as harmful data being displayed to users.
- **NIST CSF Mapping**:
  - **Protect (PR)**:
    - **PR.DS-5**: Implement protections against data leaks to ensure safe output handling.
  - **Detect (DE)**:
    - **DE.CM-3**: Monitor personnel activity to detect improper handling of generated outputs.
  - **Respond (RS)**:
    - **RS.CO-2**: Coordinate activities with stakeholders during and after an incident involving insecure output.

[Learn more about Insecure Output Handling](https://genai.owasp.org)

### LLM06:2025 - Excessive Agency <a name="llm06-2025---excessive-agency"></a>

- **Description**: The model's excessive autonomy may lead to unintended consequences, such as executing unauthorized actions.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.AM-1**: Identify and manage physical devices and systems within the organization to limit model autonomy.
  - **Protect (PR)**:
    - **PR.AC-1**: Manage identities and credentials for authorized devices and users to control model actions.
  - **Respond (RS)**:
    - **RS.MI-1**: Follow incident handling processes to mitigate risks associated with excessive agency.

[Learn more about Excessive Agency](https://genai.owasp.org)

### LLM07:2025 - System Prompt Leakage <a name="llm07-2025---system-prompt-leakage"></a>

- **Description**: Leakage of system-level prompts or instructions that could compromise the integrity or confidentiality of the model.
- **NIST CSF Mapping**:
  - **Protect (PR)**:
    - **PR.DS-4**: Protect data-in-transit to prevent leakage of system prompts.
  - **Detect (DE)**:
    - **DE.CM-6**: Monitor external service provider activity to detect potential prompt leakage.
  - **Respond (RS)**:
    - **RS.MI-4**: Use continuous monitoring capabilities to detect anomalies related to prompt leakage.

[Learn more about System Prompt Leakage](https://genai.owasp.org)

### LLM08:2025 - Vector and Embedding Weaknesses <a name="llm08-2025---vector-and-embedding-weaknesses"></a>

- **Description**: Exploitable weaknesses in vectors and embeddings, which could be manipulated to produce misleading results.
- **NIST CSF Mapping**:
  - **Protect (PR)**:
    - **PR.DS-7**: Use mechanisms to protect data authenticity to prevent manipulation of embeddings.
  - **Detect (DE)**:
    - **DE.DP-2**: Continuously assess data protection techniques to address weaknesses in vectors and embeddings.
  - **Respond (RS)**:
    - **RS.RP-1**: Regularly conduct response planning and update activities to mitigate vector weaknesses.

[Learn more about Vector and Embedding Weaknesses](https://genai.owasp.org)

### LLM09:2025 - Misinformation <a name="llm09-2025---misinformation"></a>

- **Description**: The generation of inaccurate, misleading, or false information that could impact decisions, credibility, or security.
- **NIST CSF Mapping**:
  - **Identify (ID)**:
    - **ID.RA-5**: Update risk assessments to reflect changes in the external environment that may lead to misinformation.
  - **Detect (DE)**:
    - **DE.CM-8**: Regularly perform vulnerability scanning to identify misinformation threats.
  - **Respond (RS)**:
    - **RS.CO-4**: Coordinate with stakeholders to manage the response to misinformation incidents.

[Learn more about Misinformation](https://genai.owasp.org)

### LLM10:2025 - Unbounded Consumption <a name="llm10-2025---unbounded-consumption"></a>

- **Description**: Uncontrolled consumption of resources by the model, leading to denial of service or other availability impacts.
- **NIST CSF Mapping**:
  - **Protect (PR)**:
    - **PR.IP-1**: Implement network security protections, including rate-limiting, to prevent resource exhaustion.
  - **Detect (DE)**:
    - **DE.CM-4**: Detect malicious code in the network environment that may contribute to unbounded consumption.
  - **Respond (RS)**:
    - **RS.MI-5**: Establish procedures to limit resource consumption and mitigate denial of service risks.

[Learn more about Unbounded Consumption](https://genai.owasp.org)

## Conclusion <a name="conclusion"></a>

Mapping the OWASP Top 10 for LLM Applications to the NIST Cybersecurity Framework helps organizations integrate LLM-specific risks into their broader cybersecurity strategy, ensuring a comprehensive approach to securing AI-driven applications. Organizations are encouraged to assess their systems against these vulnerabilities and apply appropriate NIST CSF controls to enhance their security posture.

