# SIMRANJEET SINGH DUA
**Cloud Platform Engineer**  
Oslo, Norway | +47 92281596 | simranjeetdua@gmail.com \
[LinkedIn](https://www.linkedin.com/in/simranjeet-singh-dua/) | [GitHub](https://github.com/SimranjeetSinghDua)

---

## Professional Summary
Cloud Platform Engineer with 5 years of experience architecting enterprise internal developer platforms, self-service golden paths, and automated cloud infrastructure. Comfortable and confident navigating the wider Azure cloud ecosystem alongside GCP and AWS, with a proven ability to master new services rapidly and deliver practical, production-ready solutions that strengthen platform security, reliability, and developer autonomy.

* **Cloud & Platforms:** Microsoft Azure (AKS, Key Vault, Azure Automation, Function Apps, App Service, Azure Backup, Azure Firewall), GCP, AWS, Kubernetes
* **Infrastructure & Automation:** Terraform, Ansible, GitHub Actions (Custom Actions, Reusable Workflows, Agentic Workflows), Docker, Python, Bash, PowerShell
* **Security & Authentication:** Microsoft Entra ID (Azure AD), SPA + BFF Pattern, Azure Workload Identity Federation (OIDC), Slack/GitHub Apps, Azure OpenAI API, GitOps
* **Kubernetes Ecosystem:** Deployments, Services, ReplicaSets, ConfigMaps, Secrets, Ingress Controllers, Gateway API, Traefik, AKS App Routing Addon, cert-manager, trust-manager, Cilium, Helm, Argo CD
* **Databases & Data:** PostgreSQL, Python ORMs, Fundamental SQL

---

## Professional Experience

### **Gjensidige** — Cloud Platform Engineer  
*05/2024 – Present | Oslo, Norway*
* Architected and maintained enterprise internal developer platforms, automating multi-environment infrastructure provisioning and cloud workflows using Azure, Terraform, Ansible, and Kubernetes.
* Designed, implemented, and championed secure web application authentication flows using Microsoft Entra ID and the SPA + BFF (Single Page Application + Backend for Frontend) pattern across production apps (including AI Insights and xledgerconverter) to eliminate browser token exposure.
* Developed custom Slack Apps and GitHub Apps integrated with Azure OpenAI to automate internal operational support, streamline developer onboarding, and generate validated Terraform pull requests for firewall changes.
* Engineered secure self-service deployment pipelines, passwordless OIDC authentication models, and golden paths, empowering engineering teams to deploy code safely without standing secrets.
* Operational expertise across Kubernetes primitives (Deployments, Services, ReplicaSets, ConfigMaps, Secrets), ingress and routing (Ingress Controllers, Gateway API, Traefik Gateway, AKS App Routing Addon), certificate automation (cert-manager, trust-manager), Helm, Argo CD, and Cilium CNI with eBPF.

### **HCL Tech** — Cloud Specialist  
*01/2023 – 05/2024 | Oslo, Norway*
* Managed Linux system administration and cloud infrastructure operations across Google Cloud Platform (GCP) environments.
* Automated infrastructure provisioning and configuration management workflows using Terraform, Ansible, and Python.

### **Tech Agrim** — Software Engineer Intern  
*10/2022 – 12/2022 | Lierstranda, Norway*
* Performed Linux system administration and cloud operations within AWS environments.
* Developed Python automation scripts to streamline internal engineering tasks.

### **Infosys** — System Engineer  
*09/2020 – 07/2021 | Pune, India*
* Administered enterprise Linux systems and cloud infrastructure services on AWS.
* Wrote Python automation utilities and maintained infrastructure configuration scripts.

---

## Key Engineering Projects & Contributions

### 1. Secure, Passwordless GitHub Authentication for Pipelines (Ephemeral Token Generator)
*Technologies: Azure Workload Identity Federation (OIDC), Azure Key Vault, GitHub Apps, GitHub Actions*
* Designed and implemented a Zero-Trust cross-repository authentication model used team-wide across Gjensidige, eliminating long-lived credentials and periodic secret rotation across GitHub repositories.
* Leveraged Azure workload identity federation so pipelines prove their runtime identity to Azure, retrieve centralized Key Vault credentials, and dynamically mint temporary GitHub App access tokens scoped to specific repositories with a 1-hour expiry.
* Governed multi-repository access via a centralized JSON organization variable mapping repositories to permissions, reviewed through platform pull requests.
* **Impact:** Strengthened supply chain security, eliminated standing secrets at rest, and removed recurring manual secret rotation overhead.

### 2. Webhook Security for Azure Automation Runbooks & Key Vault Notifications
*Technologies: Azure Automation, Azure Key Vault, PowerShell, Python, Webhooks*
* Identified and remediated a security vulnerability in automated Key Vault secret and certificate expiry notification workflows triggered via Azure web endpoints, where knowledge of the endpoint URL alone could trigger notifications.
* Designed and implemented a security framework for Azure Automation webhooks enforcing mandatory secret token validation and custom runbook header checks on every incoming request before execution.
* Centralized and secured authentication tokens inside Azure Key Vault rather than hardcoding or exposing credentials in application code, rejecting all unauthorized external calls.
* **Impact:** Eliminated unauthorized notification triggers, mitigated phishing risks from fraudulent expiry alerts, and strengthened the security and reliability of automated webhook endpoints.

### 3. Python Dispatcher for Azure Automation Hybrid Worker Package Management
*Technologies: Python, Azure Automation Hybrid Runbook Workers, Virtual Environments (venv), Linux/Windows*
* Developed a custom Python dispatcher for Azure Automation Hybrid Workers to manage isolated Python virtual environments per automation workload rather than relying on shared global system packages.
* Automated dependency resolution and isolation across runbooks, eliminating version conflicts and manual package maintenance on Hybrid Worker nodes.
* **Impact:** Improved runbook execution reliability, prevented cross-project dependency conflicts, and streamlined package lifecycle management across Hybrid Workers.

### 4. AI-Powered Firewall Change Automation (Agentic GitHub Workflows)
*Technologies: Terraform, GitHub Actions, GitHub Agentic Workflows, Azure OpenAI, Azure Firewall*
* Developed an AI-powered self-service workflow enabling teams to submit structured firewall change requests through forms/issues, with an AI agent drafting convention-compliant Terraform pull requests in our github firewall repo.
* Designed the agent to run inside a tightly restricted sandbox with read-only repository and issue access, approved command execution, and network destination allowlisting.
* Isolated write operations to deterministic, predefined actions (creating PRs, pushing to the PR branch, and updating PRs) via an elevated verification job, integrating automated Terraform plan dry runs and mandatory Security team reviews before apply.
* **Impact:** Removed manual DevOps bottlenecks, accelerated firewall delivery, and maintained strict auditability and security boundaries.

### 5. Automated Azure Backup Platform
*Technologies: Terraform, GitHub Actions, Python, Azure Native Backup Service, Azure Automation*
* Designed and implemented a fully automated, infrastructure-as-code backup platform across test and production environments, ensuring critical business data remains protected without manual intervention.
* Overcame a key limitation in Terraform's declarative model—where backups could be deleted alongside removed source resources—by making the backup vault the source of truth so backups survive accidental or malicious deletion and require an explicit removal decision.
* Established automated scheduled backup coverage for Azure disks, virtual machines, blobs, file shares, and PostgreSQL databases with automatic onboarding for new resources and configuration-based exclusions for team opt-outs.
* Built custom backup automation runbooks for scenarios not supported by Azure Native Backup, ensuring consistent, code-reviewed, and repeatable execution across environments.
* **Impact:** Improved business continuity and data protection, reduced operational overhead, and eliminated the risk of backups being unintentionally removed alongside their source resources.

### 6. AI-Powered Operations and Support Assistant in Slack
*Technologies: Slack API, Azure OpenAI API, Python, Microsoft Entra ID, Azure App Service, GitHub API*
* Built and deployed an AI-powered assistant (`operations-support-bot` in `#squad-operations`) integrated into Slack channels, threads, and direct messages to answer operational and platform support questions.
* Built an automated ingestion and scheduled synchronization pipeline aggregating internal knowledge from Slack conversations, Confluence pages, websites, and GitHub Markdown documentation, alongside live retrieval from GitHub repositories, issues, PRs, and Actions workflow runs.
* Engineered strict hallucination controls so the assistant abstains from answering in public channels when context is insufficient and transparently communicates uncertainty in direct messages.
* **Impact:** Provided reliable self-service support, reduced recurring interruptions for platform engineers, and minimized unreliable AI responses.

### 7. Cross-Repo Infrastructure Provisioning Golden Path
*Technologies: GitHub Reusable Actions, GitHub Apps, Azure OIDC Federation, Terraform, Python, JQ*
* Designed an event-driven requestor-fulfiller model for cross-repo self-service infrastructure provisioning using GitHub `repository_dispatch` events, packaged as a golden path with reusable composite GitHub Actions, Terraform, and Python.
* Replaced direct repository access and Personal Access Tokens (PATs) with a secure dispatcher-handler pattern backed by Azure Key Vault short-lived tokens and OIDC federated identities.
* Automated JSON-to-tfvars payload deep-merging via a custom Python GitHub Action to generate automated pull requests and Terraform plan reviews.

### 8. Enterprise Ansible Execution Platform on AKS
*Technologies: Ansible, GitHub Actions, Azure Kubernetes Service (AKS), Containerization, Python*
* Architected an internal Ansible Execution Platform targeting VMs using reusable workflows and custom runner images on AKS, replicating enterprise features of Ansible Tower without licensing overhead.
* Implemented dry-run capabilities, controlled deployments, automated linting, and pip/Ansible Galaxy dependency management within custom AKS runner containers.
* Secured platform access with custom onboarding logic and comprehensive workflow audit logging.

### 9. Enterprise Adoption of Secure SPA + BFF Authentication Pattern
*Technologies: Microsoft Entra ID, Single Page Applications (SPA), Backend for Frontend (BFF), OAuth 2.0 / OIDC*
* Promoted and supported engineering teams in adopting the SPA + BFF architecture so authentication flows and sensitive access tokens remain server-side rather than exposed in browser storage.
* Guided production adoption across key applications, while actively coaching additional teams through architectural transitions.
* **Impact:** Reduced exposure to browser-based token theft and account takeover risks while establishing a repeatable security standard.

---

## Education
* **Master's in Information Security (2-Year Programme)** | NTNU, Gjøvik, Norway *(08/2021 – 12/2023)*
* **Bachelor of Technology in Computer Science (4-Year Programme)** | Guru Gobind Singh IP University, New Delhi, India *(08/2015 – 08/2019)*

---

## Certifications
* Google Cloud Certified Professional Cloud Architect
* Google Cloud Certified Associate Cloud Engineer
* AWS Certified SysOps Administrator – Associate
* Cisco Certified Network Associate (CCNA) in Routing & Switching
* Cisco Certified Network Associate (CCNA) in Security

---

## Languages & References
* **Languages:** English (Professional Working Proficiency) • Norwegian (B1 – Norskprøve muntlig)
* **References:**
  * **Rida Aatif** — Head of Cloud Operations, Gjensidige | rida.aatif@gmail.com | +47 97692834
  * **Ritesh Grover** — Cloud Solutions Architect, Gjensidige | ritesh_grover2000@yahoo.com | +47 48677768
