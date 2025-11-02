## DevSecOps Lifecycle:

| **Stage**                             | **Purpose (What)**                                  | **Why (Use)**                                            | **Tools & Technologies Used**                                  | **Security Tools & Technologies Used**                                                                  |
| ------------------------------------- | --------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **1. Code & Commit**                  | Develop and version control secure code.            | Embed secure coding & scanning early.                    | Git, GitHub, GitLab, Bitbucket, VS Code, IntelliJ              | SonarQube (SAST), Checkmarx, Semgrep, Bandit, Brakeman, Snyk Code, CodeQL                               |
| **2. Build & Integrate (CI)**         | Automate build, compile & dependency management.    | Detect vulnerabilities in dependencies & builds.         | Jenkins, GitLab CI/CD, GitHub Actions, CircleCI, Maven, Gradle | OWASP Dependency-Check, Trivy, Anchore, Clair, Snyk, JFrog Xray                                         |
| **3. Test (Functional + Security)**   | Validate code quality, logic & app security.        | Identify runtime & logic-based vulnerabilities.          | Selenium, JUnit, PyTest, Postman, Cucumber                     | OWASP ZAP (DAST), Burp Suite, Arachni, Netsparker, Wapiti, Nessus                                       |
| **4. Deploy (CD + IaC)**              | Automate infrastructure & app deployment.           | Ensure secure provisioning & configuration.              | Terraform, Ansible, Puppet, Chef, Docker, Kubernetes, Helm     | Checkov (IaC Scanning), Terrascan, TFSec, Aqua Security, Twistlock, Sysdig Secure, OPA (Policy as Code) |
| **5. Operate (Runtime Security)**     | Manage infra & app operations securely.             | Detect misconfigurations & runtime threats.              | Kubernetes, Docker, AWS, Azure, GCP, OpenShift                 | Falco, AppArmor, SELinux, Sysmon, OSQuery, CrowdStrike Falcon, Wazuh                                    |
| **6. Monitor (Logs + Observability)** | Collect logs, monitor metrics & alert on anomalies. | Detect attacks, performance drops & incidents.           | Prometheus, Grafana, ELK Stack, Splunk, Dynatrace, Datadog     | SIEM (Splunk Enterprise Security, QRadar, Wazuh), IDS/IPS, CloudTrail, GuardDuty                        |
| **7. Feedback & Improve**             | Feed insights back for continuous hardening.        | Continuous security enhancement & vulnerability closure. | Jira, Confluence, ServiceNow, Git Issues, Slack Integrations   | DefectDojo, Security Scorecards, Threat Modeling Tools, RiskSense                                       |

---

### 💡 **Security Integration Flow**

```
Code → (SAST) → Build → (Dependency Scan) → Test → (DAST) → Deploy → (IaC Scan + Policy Check) → Operate → (Runtime Security) → Monitor → (SIEM + Alerts) → Feedback → Improve
```

---

### 🧠 **Key Security Testing Focus**

| **Phase** | **Primary Security Test** | **Purpose**                                |
| --------- | ------------------------- | ------------------------------------------ |
| Code      | SAST                      | Detect insecure code patterns.             |
| Build     | Dependency Scan           | Identify vulnerable libraries/packages.    |
| Test      | DAST + API Security       | Find runtime & logical vulnerabilities.    |
| Deploy    | IaC & Container Security  | Prevent misconfigurations and weak images. |
| Operate   | Runtime Protection        | Detect live attacks or anomaly behavior.   |
| Monitor   | Threat Detection & SIEM   | Correlate, alert, and analyze incidents.   |
| Improve   | Security Analytics        | Enhance policies & fix root causes.        |

---

### ⚙️ **Key Concept Summary**

1. **Shift-Left Security:** Integrate checks early (Code/Build).
2. **Continuous Scanning:** Automate SAST, DAST, IaC scans in pipeline.
3. **Policy-as-Code:** Enforce compliance via OPA/Kyverno.
4. **Runtime Defense:** Monitor with Falco, Wazuh, and Cloud workload protection.
