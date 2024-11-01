# OWASP Top 10 for Large Language Model Applications 2025  Mapped to CWE and CVE 

This repo maps vulnerabilities from the OWASP Top 10 for LLM Applications 2025 to corresponding [**Common Weakness Enumerations (CWEs)**](https://cwe.mitre.org/) and [**Common Vulnerabilities and Exposures (CVEs)**](https://www.cve.org/). This mapping provides insight into attack vectors, mitigation strategies, and security frameworks. We understand vulnerabilities in the wild are coming up every day, use the mapping as a reference and keep vigilant on new developments.




| **Vulnerability**                      | **CWE**                                                                                   | **CVE**                                                                 | **Suggested Improvements**                                                   |
|------------------------------------|----------------------------------------------------------------------------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------|
| LLM01:2025 Prompt Injection        | [CWE-20: Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html)  <br> [CWE-94: Improper Control of Code Generation](https://cwe.mitre.org/data/definitions/94.html) | [CVE-2024-5184](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-5184) | - Implement input sanitization with regular expressions. <br> - Use OWASP ZAP for input validation testing.           |
| LLM02:2025 Sensitive Information Disclosure | [CWE-200: Exposure of Sensitive Information](https://cwe.mitre.org/data/definitions/200.html)  <br> [CWE-201: Insertion of Sensitive Information Into Logs](https://cwe.mitre.org/data/definitions/201.html) | [CVE-2019-20634](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-20634) | - Use output sanitization and redaction tools for sensitive data. <br> - Implement logging controls to limit sensitive information exposure.          |
| LLM03:2025 Supply Chain Vulnerabilities | [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)  <br> [CWE-119: Improper Restriction of Operations within Buffer Bounds](https://cwe.mitre.org/data/definitions/119.html) | [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228)  <br> [CVE-2022-22965](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-22965) | - Monitor and validate dependencies with SBOM (e.g., CycloneDX). <br> - Implement automated dependency checks. |
| LLM04:2025 Data and Model Poisoning | [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)  <br> [CWE-1021: Improper Data Validation](https://cwe.mitre.org/data/definitions/1021.html) | None                                                                | - Apply strict validation on training data. <br> - Use anomaly detection for model inputs.          |
| LLM05:2025 Insecure Output Handling | [CWE-79: Cross-site Scripting (XSS)](https://cwe.mitre.org/data/definitions/79.html)  <br> [CWE-116: Improper Output Encoding](https://cwe.mitre.org/data/definitions/116.html) | [CVE-2020-8193](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8193)  <br> [CVE-2021-21234](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21234) | - Encode all outputs to prevent XSS attacks. <br> - Validate HTML responses using OWASP HTML Sanitizer.   |
| LLM06:2025 Excessive Agency        | [CWE-862: Missing Authorization](https://cwe.mitre.org/data/definitions/862.html)     | None                                                                | - Implement access controls to restrict unauthorized actions. <br> - Regularly review permission levels.             |
| LLM07:2025 System Prompt Leakage   | [CWE-209: Error Message Sensitive Information Exposure](https://cwe.mitre.org/data/definitions/209.html) | None                                                                | - Use strict prompt management policies. <br> - Avoid exposure of system prompts by using controlled logging.       |
| LLM08:2025 Vector and Embedding Weaknesses | [CWE-682: Incorrect Calculation](https://cwe.mitre.org/data/definitions/682.html)     | None                                                                | - Regularly validate embeddings for stability. <br> - Implement monitoring for anomalies in embeddings.    |
| LLM09:2025 Misinformation          | [CWE-84: Improper Neutralization of Encoded Information](https://cwe.mitre.org/data/definitions/84.html)  <br> [CWE-346: Origin Validation Error](https://cwe.mitre.org/data/definitions/346.html) | None                                                                | - Incorporate fact-checking for high-stakes outputs. <br> - Use human oversight for sensitive outputs.   |
| LLM10:2025 Unbounded Consumption   | [CWE-400: Uncontrolled Resource Consumption](https://cwe.mitre.org/data/definitions/400.html) | [CVE-2016-10033](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-10033)  <br> [CVE-2018-1002105](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-1002105) | - Monitor resources and set response limits for efficiency. <br> - Use rate limiting to control resource use.  |


---

## [LLM01:2025 Prompt Injection](https://genai.owasp.org/)
Prompt injection occurs when malicious inputs manipulate model behaviour, bypass safety measures, or trigger unauthorized actions.

- **Related CWEs**:
  - [CWE-20: Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html)
  - [CWE-94: Improper Control of Code Generation](https://cwe.mitre.org/data/definitions/94.html)

- **Related CVEs**:
  - [CVE-2024-5184](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-5184): Exploited LLM prompt injection, leading to sensitive information leaks and unauthorized actions.


**Mitigation: Input Sanitization and Validation**
- Use input sanitization to filter out unexpected characters or expressions that could lead to prompt injection. Regular expressions and input validation libraries can help detect and block suspicious inputs.

**Mitigation: Use of OWASP ZAP for Input Testing**
- Run OWASP ZAP tests to identify vulnerabilities associated with user input. ZAP helps automate the detection of injection points that could compromise model integrity.

---

## [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/)
Sensitive information disclosure involves unintended exposure of personal, confidential, or proprietary data.

- **Related CWEs**:
  - [CWE-200: Exposure of Sensitive Information](https://cwe.mitre.org/data/definitions/200.html)
  - [CWE-201: Insertion of Sensitive Information Into Logs](https://cwe.mitre.org/data/definitions/201.html)

- **Related CVEs**:
  - [CVE-2019-20634](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-20634): Demonstrated leakage of training data enabling model inversion attacks.


**Mitigation: Data Masking and Redaction**
- Apply data masking or redaction to sensitive information before displaying or logging it. Redaction tools, such as pyTainr, can prevent unintentional exposure of private information.

**Mitigation: Implement Logging Controls**
- Limit logging of sensitive data by configuring logs to exclude confidential information. Use filters to ensure no sensitive data appears in error messages or log files.

---

## [LLM03:2025 Supply Chain Vulnerabilities](https://genai.owasp.org/)
Supply chain vulnerabilities involve compromised dependencies, tools, or pre-trained models used in LLMs.

- **Related CWEs**:
  - [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)
  - [CWE-119: Improper Restriction of Operations within Buffer Bounds](https://cwe.mitre.org/data/definitions/119.html)

- **Related CVEs**:
  - [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228): Log4j vulnerability exploited in LLM deployments.
  - [CVE-2022-22965](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-22965): Spring4Shell vulnerability affecting dependencies used in LLMs.


**Mitigation: Software Bill of Materials (SBOM) Validation**
- Use an SBOM tool like CycloneDX to track dependencies and ensure they are up to date. This approach can detect vulnerabilities in third-party components that might be exploited within LLM applications.

**Mitigation: Automated Dependency Scans**
- Implement tools such as Dependabot or Snyk to automate dependency checks, helping to identify vulnerable or outdated packages that may introduce supply chain risks.

---

## [LLM04:2025 Data and Model Poisoning](https://genai.owasp.org/)
Data and model poisoning involves manipulating training data to alter model behaviour.

- **Related CWEs**:
  - [CWE-506: Embedded Malicious Code](https://cwe.mitre.org/data/definitions/506.html)
  - [CWE-1021: Improper Data Validation](https://cwe.mitre.org/data/definitions/1021.html)

- **Related CVEs**:
  - No specific CVEs; primarily involves introducing biases or malicious behaviour through poisoned data.


**Mitigation: Strict Data Validation**
- Conduct rigorous validation of all training data to prevent poisoned data from being ingested by the model. Validate the source and quality of data inputs continuously to ensure reliability.

**Mitigation: Anomaly Detection in Training Data**
- Implement anomaly detection systems to flag unusual patterns or data entries that may indicate data poisoning. Automated systems can catch deviations in data early on.

---

## [LLM05:2025 Insecure Output Handling](https://genai.owasp.org/)
Insecure output handling occurs when LLM outputs are not sanitized, leading to vulnerabilities like cross-site scripting (XSS).

- **Related CWEs**:
  - [CWE-79: Cross-site Scripting (XSS)](https://cwe.mitre.org/data/definitions/79.html)
  - [CWE-116: Improper Output Encoding](https://cwe.mitre.org/data/definitions/116.html)

- **Related CVEs**:
  - [CVE-2020-8193](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8193): XSS vulnerability impacting LLM-integrated web interfaces.
  - [CVE-2021-21234](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21234): Improper output encoding leading to injection risks.


**Mitigation: Output Encoding**
- Encode all outputs to prevent cross-site scripting (XSS) vulnerabilities. Use libraries that encode characters to avoid direct HTML/JavaScript execution, such as OWASP's HTML Sanitizer.

**Mitigation: Validate HTML Responses**
- If LLM output is used in web contexts, validate HTML responses to ensure they do not contain harmful scripts. Regularly test with OWASP ZAP to catch XSS vulnerabilities.

---

## [LLM06:2025 Excessive Agency](https://genai.owasp.org/)
Excessive agency involves LLMs gaining unauthorized control over actions beyond intended capabilities.

- **Related CWEs**:
  - [CWE-862: Missing Authorization](https://cwe.mitre.org/data/definitions/862.html)

- **Related CVEs**:
  - No specific CVEs; includes unauthorized API calls by LLMs.


**Mitigation: Access Control Enforcement**
- Limit actions that the LLM can perform by implementing strict access control. Only authorized users or services should be able to perform sensitive actions or access restricted data.

**Mitigation: Regular Permission Review**
- Periodically review and audit permissions associated with the LLM's functions to minimize excessive agency and prevent unauthorized access.

---

## [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/)
System prompt leakage involves exposing system-level instructions that control LLM behaviour.

- **Related CWEs**:
  - [CWE-209: Error Message Sensitive Information Exposure](https://cwe.mitre.org/data/definitions/209.html)

- **Related CVEs**:
  - No specific CVEs; often discussed in research on prompt leakage via inference.


**Mitigation: Prompt Management and Security Policies**
- Implement a strict management policy for prompts, ensuring sensitive prompts are secured and inaccessible to unauthorized users. Control prompt visibility in logs and avoid exposing them in error messages.

**Mitigation: Controlled Logging of System Prompts**
- Prevent sensitive prompts from being included in logs. Use controlled logging policies to ensure sensitive prompt data remains inaccessible.

---

## [LLM08:2025 Vector and Embedding Weaknesses](https://genai.owasp.org/)
Vector and embedding weaknesses involve vulnerabilities in LLM embeddings, leading to manipulation or evasion.

- **Related CWEs**:
  - [CWE-682: Incorrect Calculation](https://cwe.mitre.org/data/definitions/682.html)

- **Related CVEs**:
  - No specific CVEs; primarily involves adversarial inputs exploiting embedding weaknesses.


**Mitigation: Embedding Validation**
- Regularly validate embeddings to ensure they fall within expected ranges. Implement bounds-checking to detect and prevent out-of-range embeddings that could lead to manipulation or misinterpretation.

**Mitigation: Anomaly Monitoring for Embeddings**
- Use monitoring tools to track embedding behavior and detect anomalies that may indicate manipulation attempts. Embedding stability checks are essential for securing model interactions.

---

## [LLM09:2025 Misinformation](https://genai.owasp.org/)
Misinformation occurs when LLMs generate incorrect, misleading, or unsafe information, impacting trust and decision-making.

- **Related CWEs**:
  - [CWE-84: Improper Neutralization of Encoded Information](https://cwe.mitre.org/data/definitions/84.html)
  - [CWE-346: Origin Validation Error](https://cwe.mitre.org/data/definitions/346.html)

- **Related CVEs**:
  - No specific CVEs; often due to flaws in training or contextual interpretation.


**Mitigation: Fact-Checking Mechanisms**
- Incorporate automated fact-checking tools to validate the information generated by the LLM, especially in high-stakes or sensitive applications. Fact-checking reduces the risk of spreading misinformation.

**Mitigation: Human Oversight for Critical Outputs**
- Enable human review for outputs involving sensitive or critical information. Adding a human-in-the-loop approach helps ensure accuracy and trustworthiness.

---

## [LLM10:2025 Unbounded Consumption](https://genai.owasp.org/)
Unbounded consumption refers to excessive resource consumption (e.g., memory, processing), leading to denial of service (DoS).

- **Related CWEs**:
  - [CWE-400: Uncontrolled Resource Consumption](https://cwe.mitre.org/data/definitions/400.html)

- **Related CVEs**:
  - [CVE-2016-10033](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-10033): DoS vulnerability through excessive resource consumption.
  - [CVE-2018-1002105](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-1002105): Resource exhaustion vulnerability impacting LLM server-side implementations.


**Mitigation: Resource Monitoring and Rate Limiting**
- Set up resource monitoring and apply rate limits to control memory and CPU usage. Use tools like Kubernetes or Docker resource management to prevent unbounded consumption.

**Mitigation: Set Response Limits for Efficiency**
- Limit the number of responses or the size of responses generated by the LLM to conserve resources. This can be configured directly within the LLM or through API settings.

---

In today's rapidly evolving threat landscape, mapping CWE and CVE data to the OWASP Top 10 for LLM Applications is essential for security professionals to identify, understand, and mitigate vulnerabilities effectively. We encourage professionals to remain vigilant and proactive, continuously monitoring for emerging threats to stay informed and prepared for new security challenges in LLM applications.
