## 1. Source Code Storage: `To store code`
- eg. GitHub Repos via Git, SVN (TortoiseSVN & Apache SVN)
> Gittyleaks to scan the commits of a repo for sensitive information.

## 2. Dependency Management: `Manage library & SDKs`
- Eg. JFrog Artifactory, Azure Artufactory
- 3rd Party Lib/Dependencies eg. jQuery, Log4J, PiPy (python public dependency repo)

## 3. Automated Testing:
- Unit(smaller parts testing), Integration (how the small parts work together), Security Testing(SAST/Source Code Review, DAST By exe code)
- Penetration Testing (Manually Testing application for Contextual Vulnerabilities)

## 4. Continuous Integration and Continuous Delivery `CI/CD`:
- An Automated process `to compile, build, integrate & deploy` new software features.
- It has these ACTIONS `Starting Trigger, Building Actions, Testing Actions, Deployment Actions, Delivery Actions`.

> A Build Orchestrator directs the various agents to perform the ACTIONS of the CI/CD pipelines as required.

- Tools: Build Agents(GitHub), Runner Application (Gitlab), More Complex (Jenkins), CircleCI(Easy) etc


## 5. Environments: `Infrastructure`
- Dev < UAT (User Acceptance Testing) < PreProd < Prod < DR/HA (Diaster Recovery or High Availability)
> Security & Stability is Lowest @Dev & Highest @prod/DR/HA Environments.
- These Env can be VMs thru tools Terraform, Vagrant.
- Moreover, Move away from Hosts entirely using Containers using Docker, Pods using Kubernetes.


---

```
CI/CD = Process that automates build, Integrate, test, and deploy steps.

CI = Merge & Test code automatically (on GitHub/GitLab).

CD = Package & Deploy code to production (e.g., server, Play Store).

GitHub/GitLab = Code repo + CI/CD trigger, not the final delivery.

Play Store = Final release platform for end-users.
```

> “Git is the garage → CI/CD is the mechanic → Play Store is the showroom.”

- GitLab: GitLab is a full DevSecOps platform. It provides the code repository, but also includes its own built-in tools for Continuous Integration/Continuous Delivery (CI/CD), issue tracking, and security scanning (like SCA), all in one package. When an external tool integrates with GitLab, it's connecting to this unified platform, which can be either the public GitLab.com service or a self-hosted instance.
