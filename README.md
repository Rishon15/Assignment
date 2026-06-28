# Problem statement

Modern enterprise cloud infrastructure is highly ephemeral, decentralized, and split across multiple cloud service providers (AWS, Azure, GCP). While automated scanners and security platforms successfully flag infrastructure anomalies such as a CI/CD pipeline compromise, unauthorized API access, or severe configuration drift (due to resources being ephemeral/short-lived) they fail to provide a unified, linear investigative workflow for the engineers responsible for fixing them.

When a critical infrastructure alert triggers, Security Engineers must manually cross-reference siloed platforms to map the attacker's path. They have to trace how an identity was compromised, locate the exposed API or pipeline vulnerability, and identify the impacted multi-cloud resources. Because standard platforms treat alerts as isolated events rather than a connected attack chain, engineers waste critical hours mapping dependencies and context-switching between different administrative consoles to execute a fix. This delays threat containment and increases the window of exposure for critical production environments.

The objective of this design is an **Infrastructure Alert Triage Workflow** console that aggregates multi-cloud context, visualizes the attack chain from root cause to affected asset, and enables engineering-led, automated remediation from a single pane of glass.

# User Persona: The Cloud Security Engineer

- **Role Title:** Cloud Security Engineer
    
- **Core Responsibilities:**
    
    - Securing the CI/CD deployment pipelines and cloud infrastructure code (IaC).
        
    - Hardening the identity fabric (IAM) and minimizing the attack surface across multi-cloud environments.
        
    - Investigating and engineering fixes for deep architectural security failures, critical vulnerabilities, and active infrastructure compromises.
        
- **Environment & Tools:** Works closely with DevOps and cloud architecture teams. Operates across AWS/Azure consoles, Terraform/CloudFormation, vulnerability scanners, and automated pipeline tools.
    

### **User Goals & Motivations**

- **Root-Cause Clarity:** When an infrastructure alert fires, they want to immediately know _how_ the attacker got in (e.g., an exposed API key or a hijacked SSO token) and _what_ blast radius it affects across the multi-cloud ecosystem.
    
- **Infrastructure-as-Code Remediation:** They don't just want to "close a ticket." They want to execute a permanent fix—such as revoking an over-privileged machine identity or tearing down a drifted configuration—ideally through automated actions or direct code changes.
    

### **Key User Pain Points & Frustrations**

- **Siloed Multi-Cloud Telemetry:** Frustration with switching between AWS GuardDuty, Azure Security Center, and third-party scanners to piece together an attack that crosses cloud boundaries.
    
- **Lack of Identity & Asset Context:** Alerts that say _"Unauthorized API call detected"_ without showing which specific IAM role or automated service identity was hijacked, forcing a lengthy manual lookup.
    
- **Manual, High-Friction Mitigation:** Having to manually log into a specific cloud provider's console to terminate a compromised asset or strip permissions, introducing human error and slowing down response times during an active architectural exploit.

Link to figma designed wireframes for [assignment](https://www.figma.com/design/zftFAtVT51OA3Yx4cIstIj/Assignment?node-id=26-48&t=KGNIaajDvAksLiPZ-1)
