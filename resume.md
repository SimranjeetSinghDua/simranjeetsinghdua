# SIMRANJEET SINGH DUA

**Cloud Platform Engineer**

Oslo, Norway | +47 92281596 | simranjeetdua@gmail.com

[LinkedIn](https://www.linkedin.com/in/simranjeet-singh-dua/) | [GitHub](https://github.com/SimranjeetSinghDua)

---

## PROFESSIONAL SUMMARY

Cloud Platform Engineer with 5 years of experience building internal developer platforms, self-service golden paths, and automated cloud infrastructure. Comfortable and confident in navigating the wider Azure cloud ecosystem, with a proven ability to quickly master new services and deliver practical, production-ready solutions that empower engineering teams.

**Core Tech Stack:**

* **Cloud & Platforms:** Microsoft Azure (AKS, Key Vault, Azure Automation, Function Apps, App Service), GCP, AWS, Kubernetes
* **Infrastructure & Automation:** Terraform, Ansible, GitHub Actions (Custom Actions, Reusable Workflows), Docker, Python, Bash, PowerShell
* **Security & Authentication:** Microsoft Entra ID (Azure AD), BFF Pattern, SPA Auth, OIDC Federation, Slack/GitHub Apps, Azure OpenAI API, GitOps
* **Kubernetes Ecosystem:** Deployments, Services, ReplicaSets, ConfigMaps, Secrets, Ingress Controllers, Gateway API, Traefik, AKS App Routing Addon, cert-manager, trust-manager, Cilium, Helm, Argo CD
* **Databases:** Python ORMs and fundamental SQL

---

## PROFESSIONAL EXPERIENCE

### Gjensidige — Cloud Platform Engineer

*05/2024 – Present | Oslo, Norway*

* Architected and maintained enterprise internal developer platforms, automating infrastructure provisioning and cloud workflows using Azure, Terraform, Ansible, and Kubernetes.
* Designed and implemented secure web application authentication flows using Microsoft Entra ID, including Backend-for-Frontend (BFF) and Single Page Application (SPA) security patterns.
* Developed custom Slack Apps and GitHub Apps integrated with Azure OpenAI to handle automated internal queries, streamline developer onboarding, and accelerate team support workflows.
* Engineered secure self-service deployment pipelines and golden paths, empowering engineering teams to deploy code safely and rapidly.
* Good hands-on experience deploying applications on GAP, and with Gjensidige's core platform repositories: terraform-common-aad, terraform-azure-onboarding, terraform-azure-subscription-onboarding, terraform-github-repo-credentials, and terraform-hub-firewall.
* Good operational knowledge of Kubernetes: core primitives (Deployments, Services, ReplicaSets, ConfigMaps, Secrets), ingress and routing (Ingress Controllers, Gateway API, Traefik Gateway, AKS App Routing Addon), certificate automation (cert-manager, trust-manager), Helm, and Argo CD. Comfortable troubleshooting day-to-day issues and quickly picking up new components; currently experimenting with Cilium CNI alongside Traefik to leverage eBPF and Layer 7 benefits.

### HCL Tech — Cloud Specialist

*01/2023 – 05/2024 | Oslo, Norway*

* Managed Linux system administration and cloud infrastructure operations across Google Cloud Platform (GCP) environments.
* Automated infrastructure provisioning and configuration management workflows using Terraform, Ansible, and Python.

### Tech Agrim — Software Engineer Intern

*10/2022 – 12/2022 | Lierstranda, Norway*

* Performed Linux system administration and cloud operations within AWS environments.
* Developed Python automation scripts to streamline internal engineering tasks.

### Infosys — System Engineer

*09/2020 – 07/2021 | Pune, India*

* Administered enterprise Linux systems and cloud infrastructure services on AWS.
* Wrote Python automation utilities and maintained infrastructure configuration scripts.

---

## KEY PROJECTS

### 1. Ephemeral Cross-Repo Token Generator (Azure OIDC & GitHub App)

Designed and implemented a Zero-Trust cross-repository GitHub access solution, used team-wide across Gjensidige, that eliminates persistent secrets at rest by combining flexible Azure OIDC, Azure Key Vault, and dynamic short-lived GitHub App access token generation, with no need to rotate or store secrets in individual GitHub repositories. Replacing traditional background rotation, this decentralized pattern mints short-lived tokens at pipeline runtime driven by a centralized JSON-formatted organization variable mapping repository access, governed via platform-reviewed pull requests.

* **Zero Secrets at Rest:** Replaced static repository tokens with passwordless Azure OIDC federation, removing stored credentials entirely from GitHub settings.
* **Dynamic Access Token Generation:** Developed runtime workflows that fetch secure Key Vault credentials to dynamically generate scoped GitHub App access tokens on the fly based on the centralized configuration.
* **Centralized Governance:** Streamlined multi-repository access control using a single JSON-formatted org variable mapping repo names to permissions, managed via platform-reviewed PRs to eliminate background rotation overhead.

### 2. Cross-Repo Infrastructure Provisioning Golden Path

* **Technologies:** GitHub Reusable Actions, GitHub Apps, Azure OIDC Federation, Terraform, Python, JQ
* Designed an event-driven requestor–fulfiller model for cross-repo self-service infrastructure provisioning using GitHub `repository_dispatch` events, turned into a golden path with a reusable composite GitHub Action, Terraform, Python, automated commits, and pull requests.
* Replaced direct repository access and PATs with a secure dispatcher-handler pattern.
* Automated JSON-to-tfvars payload deep-merging via a custom Python GitHub Action, generating automated PRs and `terraform plan` reviews.
* Enforced zero standing secrets using Azure Key Vault-backed short-lived tokens and OIDC federated identities.

### 3. AI-Powered Slack Assistant & Internal Query Handler

* **Technologies:** Slack API, Azure OpenAI API, Python, Microsoft Entra ID, Azure App Service
* Built and deployed a custom Slack assistant (operations-support-bot) in the #squad-operations channel, integrated with Azure OpenAI to field, parse, and answer internal platform questions and provide troubleshooting support directly within channel feeds.
* Automated contextual troubleshooting support and documentation lookups, minimizing recurring manual interruptions for the platform engineering team.

### 4. Enterprise Ansible Execution Platform on AKS

* **Technologies:** Ansible, GitHub Actions, AKS, Containerization, Python
* Architected an internal Ansible Execution Platform to operate on VMs using reusable workflows and custom runner images on automatic AKS, replicating best practices from the terraform-plan-and-apply workflows with support for dry runs and controlled deployments.
* Used custom GitHub Actions and Community Ansible to replicate enterprise features of Ansible Tower without licensing overhead.
* Built and managed custom runner images on AKS, integrating automated linting and pip/Ansible Galaxy package management.
* Secured access using custom onboarding logic and rigorous workflow audit logging.

### 5. Agentic GitHub Workflows for Automated Terraform PRs

* **Technologies:** Terraform, GitHub Actions, GitHub Agentic Workflows, Azure OpenAI, Azure Firewall
* Built AI-assisted self-service using GitHub Agentic Workflows that converts structured GitHub issues into validated, convention-compliant Terraform pull requests in the terraform-hub-firewall repository.
* Enforced strict security boundaries by running the AI agent with a read-only token, isolating code-push capabilities to a separate elevated verification job.
* Reduced security review overhead by turning manual rule authoring into single-click PR reviews while preserving mandatory human approvals.

### 6. Automated Multi-Environment Backup Service & Webhook Security

* **Technologies:** GitHub Actions, Terraform, Python, Azure Native Backup Service, Azure Automation, Azure Key Vault
* Designed an automated Azure resource backup service with automatic resource discovery and handling of deleted resources for dynamic cloud environments.
* Built custom backup automation runbooks for scenarios not supported by Azure Native Backup.
* Built a security framework for Azure Automation webhooks using token validation, custom runbook header checks, and secure token storage in Azure Key Vault to prevent unauthorized external calls.
* Developed a Python dispatcher for Azure Automation Hybrid Workers supporting isolated Python virtual environments and more reliable dependency management.

---

## EDUCATION

* **Master’s in Information Security (2-Year Programme)** | NTNU, Gjøvik, Norway *(08/2021 – 12/2023)*
* **Bachelor of Technology in Computer Science (4-Year Programme)** | Guru Gobind Singh IP University, New Delhi, India *(08/2015 – 08/2019)*

---

## CERTIFICATIONS

* **Google Cloud Certified Professional Cloud Architect**
* **AWS Certified SysOps Administrator – Associate**
* **Google Cloud Certified Associate Cloud Engineer**
* **Cisco Certified Network Associate in Routing & Switching**
* **Cisco Certified Network Associate in Security**
---

## LANGUAGES

* **English:** Professional Working Proficiency (Second Language)
* **Norwegian:** B1 (Norskprøve muntlig)

---

## REFERENCES

* Rida Aatif, Head of Cloud Operations, Gjensidige \
rida.aatif@gmail.com, +4797692834
* Ritesh Grover, Cloud Solutions Architect, Gjensidige \
ritesh_grover2000@yahoo.com, +4748677768
