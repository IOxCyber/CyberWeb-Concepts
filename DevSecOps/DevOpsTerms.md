## 1. Source Code Storage: To store code
- eg. GitHub Repos via Git, SVN (TortoiseSVN & Apache SVN)
- GitLab (to host your own git server)
> Gittyleaks to scan the commits of a repo for sensitive information.

## 2. Dependency Management: Manage library & SDKs
- Eg. JFrog Artifactory, Azure Artufactory
- 3rd Party Lib/Dependencies eg. jQuery, Log4J, PiPy (python public dependency repo)

## 3. Automated Testing:
- Unit(smaller parts testing), Integration (how the small parts work together), Security Testing(SAST/Source Code Review, DAST By exe code)
- Penetration Testing (Manually Testing application for Contextual Vulnerabilities)

## 4. Continuous Integration and Delivery:
- An Automated process to compile, build, integrate & deploy new software features.
- It has these ACTIONS `Starting Trigger, Building Actions, Testing Actions, Deployment Actions, Delivery Actions`.

> A Build Orchestrator directs the various agents to perform the ACTIONS of the CI/CD pipelines as required.

- Tools: Build Agents(GitHub), Runner Application (Gitlab), More Complex (Jenkins)


## 5. 