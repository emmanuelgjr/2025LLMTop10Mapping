# OWASP Top 10 for Large Language Model Applications 2025  Mapping to CVE and CWE 

This document maps vulnerabilities from the OWASP Top 10 for LLM Applications 2025 to corresponding Common Vulnerabilities and Exposures (CVEs) and Common Weakness Enumerations (CWEs). This mapping provides insight into attack vectors, mitigation strategies, and security frameworks.

## Table of Contents
1. [LLM01:2025 Prompt Injection](https://genai.owasp.org/)
2. [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)
3. [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)
4. [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)
5. [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)
6. [LLM06:2025 Excessive Agency](https://genai.owasp.org/)
7. [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)
8. [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)
9. [LLM09:2025 Misinformation](https://genai.owasp.org/)
10. [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)

## LLM01:2025 Prompt Injection
Prompt injection occurs when malicious inputs manipulate model behavior, bypass safety measures, or trigger unauthorized actions.

- **Related CVEs**:
  - [CVE-2024-5184](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-5184): Exploited LLM prompt injection, leading to sensitive information leaks and unauthorized actions.
- **Related CWEs**:
  - [CWE-20: Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html)
  - [CWE-94: Improper Control of Code Generation](https://cwe.mitre.org/data/definitions/94.html)

## LLM02:2025 Sensitive Information Disclosure
Sensitive information disclosure involves unintended exposure of personal, confidential, or proprietary data.

- **Related CVEs**:
  - [CVE-2019-20634](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-20634): Demonstrated leakage of training data enabling model inversion attacks.
- **Related CWEs**:
  - [CWE-200: Exposure of Sensitive Information](https://cwe.mitre.org/data/definitions/200.html)
  - [CWE-201: Insertion of Sensitive Information Into Logs](https://cwe.mitre.org/data/definitions/201.html)

## LLM03:2025 Supply Chain Vulnerabilities
Supply chain vulnerabilities involve compromised dependencies, tools, or pre-trained models used in LLMs.

- **Related CVEs**:
  - [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228): Log4j vulnerability exploited in LLM deployments.
  - [CVE-2022-22965](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-22965): Spring4Shell vulnerability affecting dependencies used in LLMs.
- **Related CWEs**:
  - [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)
  - [CWE-119: Improper Restriction of Operations within Buffer Bounds](https://cwe.mitre.org/data/definitions/119.html)

## LLM04:2025 Data and Model Poisoning
Data and model poisoning involves manipulating training data to alter model behavior.

- **Related CVEs**:
  - No specific CVEs; primarily involves introducing biases or malicious behavior through poisoned data.
- **Related CWEs**:
  - [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)
  - [CWE-1021: Improper Data Validation](https://cwe.mitre.org/data/definitions/1021.html)

## LLM05:2025 Insecure Output Handling
Insecure output handling occurs when LLM outputs are not sanitized, leading to vulnerabilities like cross-site scripting (XSS).

- **Related CVEs**:
  - [CVE-2020-8193](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8193): XSS vulnerability impacting LLM-integrated web interfaces.
  - [CVE-2021-21234](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21234): Improper output encoding leading to injection risks.
- **Related CWEs**:
  - [CWE-79: Cross-site Scripting (XSS)](https://cwe.mitre.org/data/definitions/79.html)
  - [CWE-116: Improper Output Encoding](https://cwe.mitre.org/data/definitions/116.html)

## LLM06:2025 Excessive Agency
Excessive agency involves LLMs gaining unauthorized control over actions beyond intended capabilities.

- **Related CVEs**:
  - No specific CVEs; includes unauthorized API calls by LLMs.
- **Related CWEs**:
  - [CWE-862: Missing Authorization](https://cwe.mitre.org/data/definitions/862.html)

## LLM07:2025 System Prompt Leakage
System prompt leakage involves exposing system-level instructions that control LLM behavior.

- **Related CVEs**:
  - No specific CVEs; often discussed in research on prompt leakage via inference.
- **Related CWEs**:
  - [CWE-209: Error Message Sensitive Information Exposure](https://cwe.mitre.org/data/definitions/209.html)

## LLM08:2025 Vector and Embedding Weaknesses
Vector and embedding weaknesses involve vulnerabilities in LLM embeddings, leading to manipulation or evasion.

- **Related CVEs**:
  - No specific CVEs; primarily involves adversarial inputs exploiting embedding weaknesses.
- **Related CWEs**:
  - [CWE-682: Incorrect Calculation](https://cwe.mitre.org/data/definitions/682.html)

## LLM09:2025 Misinformation
Misinformation occurs when LLMs generate incorrect, misleading, or unsafe information, impacting trust and decision-making.

- **Related CVEs**:
  - No specific CVEs; often due to flaws in training or contextual interpretation.
- **Related CWEs**:
  - [CWE-84: Improper Neutralization of Encoded Information](https://cwe.mitre.org/data/definitions/84.html)
  - [CWE-346: Origin Validation Error](https://cwe.mitre.org/data/definitions/346.html)

## LLM10:2025 Unbounded Consumption
Unbounded consumption refers to excessive resource consumption (e.g., memory, processing), leading to denial of service (DoS).

- **Related CVEs**:
  - [CVE-2016-10033](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-10033): DoS vulnerability through excessive resource consumption.
  - [CVE-2018-1002105](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-1002105): Resource exhaustion vulnerability impacting LLM server-side implementations.
- **Related CWEs**:
  - [CWE-400: Uncontrolled Resource Consumption](https://cwe.mitre.org/data/definitions/400.html)

We encourage professionals to stay vigilant and continuously monitor the evolving threat landscape to remain informed about emerging vulnerabilities and security developments.
