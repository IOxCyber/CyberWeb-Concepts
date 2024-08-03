# Active Directory
- Active Directory (AD) is a directory service developed by Microsoft for Windows domain networks.
-  `Active Directory contains information about user accounts, such as usernames, passwords, and permissions.`
-  The domain controller uses it to authenticate users and manage access to resources.

## **Function**:
1. **Centralized Resource Management**: Stores information about objects on the network and makes this information easy for administrators and users to find and use.
2. **Hierarchy**: Organizes resources in a hierarchical structure, including domains, trees, and forests.
3. **Policy Management**: Allows the administration of user and computer policies.

## **Components**:
- **AD DS (Active Directory Domain Services)**: Provides directory services including authentication and authorization.
- **AD LDS (Active Directory Lightweight Directory Services)**: Lightweight version of AD DS.
- **AD FS (Active Directory Federation Services)**: Provides single sign-on (SSO) capabilities.
- **AD CS (Active Directory Certificate Services)**: Manages public key infrastructure (PKI).

# Domain Controller
- A domain controller (DC) is a server in a Windows network that `responds to authentication requests and verifies users on the network.`

## Function:
1. **User Authentication**: Verifies user credentials and provides access to network resources.
2. **Security Policies**: Enforces security policies across the network.
3. **Replication**: Shares information between other domain controllers to ensure consistency.

**Example**: In a corporate network, when a user logs in to their workstation, the domain controller verifies their username and password against the stored credentials in the Active Directory.

# Relationship Between Domain Controller and Active Directory

- **Dependency**: Domain controllers rely on Active Directory to store and manage user data, group policies, and network resource information.
- **Integration**: Active Directory runs on domain controllers, which serve as the backbone for user and resource management in a Windows network environment.

# Diagram Overview

```plaintext
+------------------------------------+
|           Active Directory         |
|                                    |
|  +------------------------------+  |
|  | Domain Controller 1          |  |
|  | - User Authentication        |  |
|  | - Policy Enforcement         |  |
|  +------------------------------+  |
|                                    |
|  +------------------------------+  |
|  | Domain Controller 2          |  |
|  | - Replication                |  |
|  | - Load Balancing             |  |
|  +------------------------------+  |
|                                    |
+------------------------------------+
