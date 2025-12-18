# 🚀 AI-Proof Sysadmin Roadmap 2025-2026
## 12-Month Career Transformation | Sophia Antipolis/Monaco

> **Commitment**: 1–2h/day | **Budget**: €0–50/month | **Focus**: Hands-on + Gamified Learning

---

## 📊 Skills Matrix (Track Your Progress)

| Skill Domain | Month 1-3 | Month 4-6 | Month 7-9 | Month 10-12 |
|-------------|-----------|-----------|-----------|-------------|
| **Cloud & IaC** | ⬜ AWS/Azure basics | ⬜ Terraform | ⬜ Multi-cloud | ⬜ FinOps |
| **Containers** | ⬜ Docker basics | ⬜ Docker Compose | ⬜ Kubernetes | ⬜ K8s security |
| **Automation** | ⬜ Bash/PowerShell | ⬜ Python basics | ⬜ Ansible | ⬜ GitOps |
| **Security** | ⬜ Hardening | ⬜ Pentesting basics | ⬜ Zero Trust | ⬜ Compliance |
| **AI/ML Ops** | ⬜ AI tools usage | ⬜ LLM integration | ⬜ MLOps basics | ⬜ AI automation |
| **Observability** | ⬜ Logs/metrics | ⬜ Prometheus/Grafana | ⬜ Tracing | ⬜ AIOps |

> **Legend**: ⬜ Not Started | 🟡 In Progress | ✅ Completed

---

## 🎮 Gamified Learning Platforms (Free/Low-Cost)

| Platform | Focus | Cost | XP System |
|----------|-------|------|-----------|
| [TryHackMe](https://tryhackme.com) | Security, Linux, Networks | Free tier + €10/mo | Ranks & Badges |
| [HackTheBox](https://hackthebox.com) | Pentesting, CTFs | Free tier | Points & Ranks |
| [KodeKloud](https://kodekloud.com) | DevOps, Kubernetes | €15/mo | Hands-on labs |
| [Killercoda](https://killercoda.com) | K8s, Docker, Linux | Free | Browser labs |
| [OverTheWire](https://overthewire.org) | Linux, Security | Free | Wargames levels |
| [PentesterLab](https://pentesterlab.com) | Web security | Free tier | Badges |
| [Cisco NetAcad](https://netacad.com) | Networking | Free | Certifications |

---

## 📅 QUARTER 1: Foundation (Months 1-3)
### Theme: *"Automate or Be Automated"*

---

### Month 1: Linux Mastery & Scripting

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W1** | Linux Deep Dive | • Complete OverTheWire Bandit (levels 0-15)<br>• Set up home lab VM (Proxmox/VirtualBox) | 🎮 OverTheWire Bandit |
| **W2** | Shell Scripting | • Bash scripting fundamentals<br>• Automate 3 daily tasks you do manually | 🧪 TryHackMe "Linux Fundamentals" |
| **W3** | PowerShell | • PowerShell for Linux admins<br>• Create cross-platform automation script | 🧪 Microsoft Learn PS labs |
| **W4** | Git & Version Control | • Git fundamentals + GitHub account<br>• Start documenting all scripts in repo | 🎮 [Learn Git Branching](https://learngitbranching.js.org) |

**🏆 Month 1 Portfolio Project**: 
> **"SysAdmin Toolkit"** - GitHub repo with 10+ automation scripts (backup, user management, log rotation, monitoring checks). Include README with usage examples.

---

### Month 2: Networking & Security Fundamentals

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W5** | Network Deep Dive | • TCP/IP, DNS, DHCP mastery<br>• Wireshark packet analysis | 🎮 TryHackMe "Network Fundamentals" |
| **W6** | Firewall & VPN | • iptables/nftables deep dive<br>• Set up WireGuard VPN for home lab | 🧪 Build VPN between 2 VMs |
| **W7** | Security Hardening | • CIS Benchmarks for Linux/Windows<br>• Implement on home lab servers | 🎮 TryHackMe "Linux PrivEsc" |
| **W8** | Intro to Pentesting | • Complete OverTheWire Bandit (levels 16-33)<br>• Nmap, enumeration basics | 🎮 HackTheBox "Starting Point" |

**🏆 Month 2 Portfolio Project**:
> **"Secure Server Baseline"** - Ansible playbook that hardens a fresh Linux server (SSH, firewall, fail2ban, auditd, CIS basics). Blog post explaining each security measure.

---

### Month 3: Cloud Foundations

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W9** | Cloud Concepts | • AWS/Azure free tier setup<br>• Core services: compute, storage, networking | 🧪 AWS Cloud Quest (free game) |
| **W10** | Cloud CLI & SDK | • AWS CLI / Azure CLI mastery<br>• Script cloud resource deployment | 🧪 [AWS Workshops](https://workshops.aws) |
| **W11** | Cloud Security | • IAM best practices<br>• Security groups, VPCs | 🎮 [flAWS Challenge](http://flaws.cloud) |
| **W12** | Cost Management | • Understand pricing models<br>• Set up billing alerts, clean up resources | 🧪 FinOps Foundation intro |

**🏆 Month 3 Portfolio Project**:
> **"Cloud Landing Zone"** - Terraform code to deploy a secure, cost-optimized 3-tier architecture on AWS/Azure free tier. Include architecture diagram.

---

## 📅 QUARTER 2: Containerization & IaC (Months 4-6)
### Theme: *"Infrastructure as Code, Not Clicks"*

---

### Month 4: Docker Mastery

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W13** | Docker Fundamentals | • Containers vs VMs<br>• Build, run, manage containers | 🧪 Killercoda Docker scenarios |
| **W14** | Dockerfile Best Practices | • Multi-stage builds<br>• Security scanning (Trivy) | 🎮 [Docker Labs](https://labs.play-with-docker.com) |
| **W15** | Docker Compose | • Multi-container applications<br>• Networking, volumes | 🧪 Deploy LAMP/LEMP stack |
| **W16** | Container Security | • Image scanning, secrets management<br>• Rootless containers | 🎮 TryHackMe "Docker" room |

**🏆 Month 4 Portfolio Project**:
> **"Containerized Monitoring Stack"** - Docker Compose deployment of Prometheus + Grafana + AlertManager with custom dashboards for sysadmin metrics.

---

### Month 5: Infrastructure as Code

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W17** | Terraform Basics | • HCL syntax, providers, resources<br>• State management | 🧪 Killercoda Terraform labs |
| **W18** | Terraform Advanced | • Modules, workspaces<br>• Remote state (S3/Azure Blob) | 🧪 [HashiCorp Learn](https://learn.hashicorp.com) |
| **W19** | Ansible Fundamentals | • Playbooks, roles, inventory<br>• Idempotency principles | 🧪 KodeKloud Ansible labs |
| **W20** | Ansible + Terraform | • Combined workflows<br>• Provisioning + configuration | 🧪 Build full infra pipeline |

**🏆 Month 5 Portfolio Project**:
> **"IaC Complete Environment"** - Terraform provisions cloud infra, Ansible configures it. Include web server, database, monitoring. All in Git with CI/CD.

---

### Month 6: Python for SysAdmins

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W21** | Python Basics | • Data types, control flow, functions<br>• File/string manipulation | 🎮 [Codewars](https://codewars.com) Python katas |
| **W22** | Python for Automation | • OS, subprocess, shutil modules<br>• API interactions (requests) | 🧪 Automate with Python book (free) |
| **W23** | Python DevOps Tools | • Boto3 (AWS), Azure SDK<br>• Fabric for SSH automation | 🧪 Build cloud inventory tool |
| **W24** | Python Projects | • Log parser, config generator<br>• Slack/Discord bot for alerts | 🧪 Real-world automation |

**🏆 Month 6 Portfolio Project**:
> **"Infrastructure Bot"** - Python bot that monitors your infrastructure, sends alerts to Discord/Slack, and can execute remediation commands via chat.

---

## 📅 QUARTER 3: Orchestration & DevOps (Months 7-9)
### Theme: *"Scale Like the Cloud Giants"*

---

### Month 7: Kubernetes Fundamentals

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W25** | K8s Architecture | • Pods, Deployments, Services<br>• kubectl mastery | 🧪 Killercoda K8s scenarios |
| **W26** | K8s Networking | • Ingress, NetworkPolicies<br>• Service mesh concepts | 🎮 [K8s The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) |
| **W27** | K8s Storage & Config | • PV/PVC, ConfigMaps, Secrets<br>• Helm charts basics | 🧪 KodeKloud CKA prep |
| **W28** | K8s in Production | • Health checks, resource limits<br>• Rolling updates, rollbacks | 🧪 Deploy real app to K8s |

**🏆 Month 7 Portfolio Project**:
> **"K8s Application Platform"** - Deploy a microservices app to local K8s (kind/k3s) with Helm, ingress, monitoring, and auto-scaling.

---

### Month 8: CI/CD & GitOps

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W29** | CI/CD Fundamentals | • GitHub Actions workflows<br>• Build, test, deploy pipelines | 🧪 [GitHub Skills](https://skills.github.com) |
| **W30** | GitLab CI/Jenkins | • Alternative CI/CD tools<br>• Self-hosted runners | 🧪 Set up GitLab CI locally |
| **W31** | GitOps with ArgoCD | • Declarative deployments<br>• Sync strategies | 🧪 Killercoda ArgoCD labs |
| **W32** | Advanced Pipelines | • Security scanning in CI<br>• Multi-environment deployments | 🧪 Build production pipeline |

**🏆 Month 8 Portfolio Project**:
> **"GitOps Pipeline"** - Complete CI/CD pipeline with GitHub Actions + ArgoCD deploying to K8s. Include security scanning, testing, multi-environment.

---

### Month 9: Observability & SRE

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W33** | Monitoring Deep Dive | • Prometheus advanced queries<br>• Custom exporters | 🧪 [Prometheus Labs](https://prometheus.io/docs/prometheus/latest/getting_started/) |
| **W34** | Logging at Scale | • ELK/Loki stack<br>• Log aggregation patterns | 🧪 Deploy Loki + Grafana |
| **W35** | Distributed Tracing | • Jaeger/OpenTelemetry<br>• Trace-based debugging | 🧪 Instrument sample app |
| **W36** | SRE Practices | • SLOs, SLIs, Error Budgets<br>• On-call and incident management | 📖 Google SRE book (free) |

**🏆 Month 9 Portfolio Project**:
> **"Full Observability Stack"** - Complete monitoring solution with Prometheus, Grafana, Loki, and alerting. Include runbooks and SLO dashboards.

---

## 📅 QUARTER 4: AI Integration & Specialization (Months 10-12)
### Theme: *"AI-Augmented, Not AI-Replaced"*

---

### Month 10: AI Tools for SysAdmins

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W37** | AI Assistants | • GitHub Copilot for scripts<br>• ChatGPT/Claude for troubleshooting | 🧪 AI-assisted automation |
| **W38** | LLM APIs | • OpenAI/Anthropic/Ollama APIs<br>• Build AI-powered tools | 🧪 Create runbook generator |
| **W39** | Local LLMs | • Ollama setup<br>• Self-hosted AI for privacy | 🧪 Private LLM for docs |
| **W40** | AIOps Basics | • Anomaly detection concepts<br>• AI for log analysis | 🧪 Integrate AI in monitoring |

**🏆 Month 10 Portfolio Project**:
> **"AI SysAdmin Assistant"** - Local Ollama-based chatbot trained on your runbooks that can answer infrastructure questions and suggest troubleshooting steps.

---

### Month 11: Security Specialization

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W41** | Zero Trust Architecture | • Identity-first security<br>• BeyondCorp concepts | 📖 Zero Trust Whitepaper |
| **W42** | Cloud Security | • AWS/Azure security tools<br>• Cloud security posture | 🎮 [CloudGoat](https://github.com/RhinoSecurityLabs/cloudgoat) |
| **W43** | Compliance & Audit | • GDPR, SOC2, ISO27001 basics<br>• Automated compliance checks | 🧪 OpenSCAP scanning |
| **W44** | CTF Deep Dive | • Advanced challenges<br>• Write-ups and documentation | 🎮 HackTheBox Pro Labs |

**🏆 Month 11 Portfolio Project**:
> **"Security Automation Framework"** - Automated security scanning pipeline with compliance checks, vulnerability reporting, and remediation suggestions.

---

### Month 12: Career Capstone

| Week | Focus | Tasks (1-2h/day) | Lab/CTF |
|------|-------|------------------|---------|
| **W45** | Portfolio Polish | • Clean up all GitHub repos<br>• Write detailed READMEs | 🧪 Documentation sprint |
| **W46** | Personal Branding | • LinkedIn optimization<br>• Tech blog posts (Medium/Dev.to) | 📝 Write 3 technical posts |
| **W47** | Certification Prep | • Choose: CKA, AWS SAA, Azure AZ-104<br>• Intensive study | 🧪 Practice exams |
| **W48** | Interview Prep | • System design practice<br>• Mock interviews | 🎮 [Pramp](https://pramp.com) mock interviews |

**🏆 Month 12 Capstone Project**:
> **"Complete Infrastructure Platform"** - Combine all learnings: IaC-deployed K8s cluster with GitOps, full observability, AI-assisted operations, security scanning. Present as portfolio centerpiece.

---

## 🇫🇷 Local Resources (Sophia Antipolis/Monaco)

### Meetups & Communities
| Event | Focus | Frequency |
|-------|-------|-----------|
| [Riviera DEV](https://rivieradev.fr) | Developer conference | Annual (May) |
| [NiceTech](https://www.meetup.com/nicetech/) | Tech meetups | Monthly |
| [French Riviera DevOps](https://www.meetup.com/french-riviera-devops/) | DevOps/Cloud | Monthly |
| [GDG Nice](https://gdg.community.dev/gdg-nice/) | Google tech | Monthly |
| [Monaco Tech](https://monacotech.mc) | Startup ecosystem | Various |

### Tech Hubs & Coworking
- **Sophia Antipolis Technopole** - Europe's largest tech park
- **Mougins**: Several tech companies and startups
- **Monaco**: Extended Monaco program for tech workers

### Companies Hiring Cloud/DevOps
- Amadeus, Thales, SAP, ARM, Orange, Capgemini
- Startups at Sophia Antipolis Business Poles
- Monaco: gaming companies, fintech

---

## 💰 Budget Breakdown

| Item | Monthly Cost | Notes |
|------|-------------|-------|
| **TryHackMe Premium** | €10 | Optional, free tier is good |
| **Cloud Free Tiers** | €0 | Stay within limits |
| **Killercoda** | €0 | Free browser labs |
| **KodeKloud** | €15 | Best value for DevOps |
| **Home Lab Electricity** | ~€10 | Old PC as Proxmox host |
| **Domain for Portfolio** | €12/year | Optional |
| **Total** | **€25-35/mo** | |

---

## 🏅 Certification Path (Optional)

| Timeline | Certification | Cost | Value |
|----------|--------------|------|-------|
| Month 6 | **Terraform Associate** | $70 | High demand |
| Month 9 | **CKA** (Kubernetes) | $395 | Industry standard |
| Month 12 | **AWS SAA** or **Azure AZ-104** | $150 | Cloud credibility |

> 💡 **Tip**: Many employers in Sophia Antipolis reimburse certification costs!

---

## 📈 Weekly Progress Tracker

```
Week [__]: ________________________
Hours Invested: [__] h
Labs Completed: [________________]
CTF Challenges: [________________]
Portfolio Update: [________________]
Key Learning: [________________]
```

---

## 🎯 Success Metrics

By Month 12, you should have:
- [ ] **10+ GitHub repositories** with quality code
- [ ] **3+ blog posts** demonstrating expertise
- [ ] **50+ CTF challenges** completed
- [ ] **1 certification** minimum
- [ ] **Full portfolio site** showcasing projects
- [ ] **LinkedIn profile** attracting recruiters
- [ ] **Local network** of 20+ tech professionals

---

> **Remember**: The goal isn't to compete with AI—it's to leverage it. The sysadmins who thrive are those who automate the repetitive, focus on architecture and strategy, and use AI as a force multiplier.

**Bonne chance! 🚀**
