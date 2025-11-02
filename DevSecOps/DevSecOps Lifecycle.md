## DevSecOps Lifecycle:
---

## 🔐 **DevSecOps Lifecycle: Code → Build → Test → Deploy → Operate → Monitor → Improve**

| **Stage**                         | **Purpose (What)**                                 | **Why (Use)**                                             | **Tools & Technologies (Examples)**                                                                                         | **Extras (Alternatives / Similar)**                    |
| --------------------------------- | -------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **1. Code & Commit**              | Write and version code securely.                   | Embed security early in SDLC.                             | 🧩 *Git*, *GitHub*, *GitLab*, *Bitbucket*, *SonarQube (SAST)*, *Checkmarx*, *Semgrep*, *Bandit (Python)*, *Brakeman (Ruby)* | *Snyk Code*, *Veracode*, *CodeQL*, *Fortify SCA*       |
| **2. Build & Integrate (CI)**     | Automate code compilation and dependency scanning. | Catch build-time vulnerabilities.                         | ⚙️ *Jenkins*, *GitLab CI/CD*, *GitHub Actions*, *CircleCI*, *TravisCI*                                                      | *Azure DevOps*, *Bamboo*, *TeamCity*                   |
| **Security in Build**             | Integrate dependency and image scanning.           | Detect known CVEs in dependencies.                        | 🧱 *OWASP Dependency-Check*, *Snyk*, *Anchore*, *Trivy*, *Clair*, *JFrog Xray*                                              | *Grype*, *BlackDuck*, *Whitesource*                    |
| **3. Test (Security + Quality)**  | Validate functionality + security of builds.       | Ensure application meets functional & security baselines. | 🧪 *JUnit*, *Selenium*, *PyTest*, *Postman*, *BurpSuite (DAST)*, *OWASP ZAP*, *Arachni*, *Nessus*                           | *Acunetix*, *Netsparker*, *Wapiti*                     |
| **4. Deploy (CD + IaC)**          | Release code securely to environments.             | Automate secure infra provisioning.                       | 🚀 *Terraform*, *Ansible*, *Puppet*, *Chef*, *Helm*, *Kubernetes*, *Docker*, *Vault*                                        | *Pulumi*, *SaltStack*, *OpenShift*, *ArgoCD*, *FluxCD* |
| **Security in Deploy**            | Scan container images + enforce policies.          | Prevent vulnerable containers from being deployed.        | 🛡️ *Aqua Security*, *Twistlock*, *NeuVector*, *Sysdig Secure*                                                              | *Kyverno*, *OPA (Open Policy Agent)*                   |
| **5. Operate (Runtime Security)** | Ensure security of running apps & infra.           | Detect runtime attacks or drift.                          | 🧠 *Falco*, *AppArmor*, *SELinux*, *Sysmon*, *OSQuery*                                                                      | *Wazuh*, *CrowdStrike Falcon*, *Datadog Security*      |
| **6. Monitor (Logs + Metrics)**   | Track performance, logs, and threats.              | Observe anomalies, detect breaches early.                 | 📊 *Prometheus*, *Grafana*, *ELK Stack (Elasticsearch, Logstash, Kibana)*, *Splunk*, *Dynatrace*                            | *Graylog*, *Datadog*, *New Relic*, *Sumo Logic*        |
| **7. Feedback & Improve**         | Feed insights back to dev teams.                   | Continuous improvement & posture hardening.               | 🔁 *Jira*, *Confluence*, *ServiceNow*, *Security Scorecards*, *DefectDojo*                                                  | *GitHub Security Dashboard*, *RiskSense*               |

---

### ⚙️ **Key Concept Summary**

1. **Shift-Left Security:** Integrate checks early (Code/Build).
2. **Continuous Scanning:** Automate SAST, DAST, IaC scans in pipeline.
3. **Policy-as-Code:** Enforce compliance via OPA/Kyverno.
4. **Runtime Defense:** Monitor with Falco, Wazuh, and Cloud workload protection.
