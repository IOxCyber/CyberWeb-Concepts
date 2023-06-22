## [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks):
- Center for Internet Security. [Download CIS](https://downloads.cisecurity.org/#/)
- Set of globally recognized and consensus-driven best practices/controls to help security practitioners implement and manage their cybersecurity defenses.
- Provides a number of security controls for different type of OS (Windows, Linux, MacOs), Network Devices(Cisco, Palo ALto Firewalls)
- <img width="500" alt="image" src="https://github.com/cybersome/CyberDev/assets/40174034/747733a2-c352-46b7-8533-6383d251009a">

## [EDR vs Antivirus](https://cybriant.com/antivirus-vs-edr/):
- `EDR` (Endpoint Detection & Response) or `[behavior-based](https://www.kaspersky.com/enterprise-security/wiki-section/products/behavior-based-protection)`[^1] endpoint protection system.
- Antivirus programs are more `simplistic and limited in scope` & work upon their DB (detects malware and viruses by `[signature-based](https://www.educative.io/answers/what-is-signature-based-detection)`[^2] detection)
- EDR contains many security tools like Antivirus, firewalls, whitelisting tools, and monitoring tools.
- EDR agent on the endpoints constantly monitors for changes in behavior that could indicate the presence of malicious software.
- Examples:
1. CrowdStrike is a cloud-based antimalware solution that offers real-time protection, network traffic analysis, advanced threat intelligence, and fileless attack mitigation.
2. Bitfender offers a variety of features, including advanced heuristics, BIOS validation, and advanced memory scanning. 
3. Webroot is an antivirus solution that is available as both an on-premise and cloud-based solution.

## Other Systems:
1. `Next-Generation Antivirus (NGAV)`: cybersecurity tool that leverages AI, ML & behavioral detection and exploit mitigation to anticipate and prevent both known and unknown threats.
2. Managed Detection and Response (MDR): Endpoint security “as a service", manages endpoint security technologies for organizations which includes EDR, guided response, managed remediation etc.
3. Extended Detection and Response (XDR): Extended Detection and Response (XDR) is a consolidation of tools and data that provides extended visibility, analysis, and response across endpoints, workloads, users, and networks.

## 




































[^1]: If a program tries to search, modify or delete some important file then it will be considered as malicious 'actions' or behaviors that are typical of malware.
[^2]: In this style of detection, unique identifiers are generated about a known attack so that any attack of that kind is rapidly dealt with.
