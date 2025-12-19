# Month 1 — Lab baseline + network segmentation + ops documentation (no Linux basics)

**Goal:** a clean, documented, repeatable homelab that looks like a small business platform.

### Week 1: “Clean baseline”

- Define naming standards (hosts, VMs, networks, VLANs)
- Create “ops repo” (docs + diagrams + inventory)
- Decide hypervisor primary: **ESXi or Proxmox** (your choice)

### Week 2: Network layout (pfSense + VLANs)

- MGMT vs LAN vs (optional) DMZ separation
- Firewall rules: *explicit allow*, logging enabled
- DNS + DHCP plan (where it lives, what’s authoritative)

### Week 3: Identity + access (practical)

- Central admin: AD/LDAP + groups for roles (admins, operators, read-only)
- Minimum: MFA on your remote access point (VPN/portal)

### Week 4: Observability baseline (so you can operate)

- Central syslog + basic dashboards (Elastic if you already run it)
- 5 alert rules: storage nearly full, host down, backup job failed, auth anomalies, high CPU/RAM

**Deliverables:** diagram + inventory + firewall policy summary + “how to access / how to troubleshoot basics”.

---

# Month 2 — Virtualization + Storage + Backups + Recovery (expanded, as requested)

**Goal:** prove you can **recover**. (This is extremely “AI-proof”.)

### Week 1: Hypervisor repeatable baseline

- Templates, snapshots, time sync, admin hygiene
- (ESXi option) practice in **VMware HOL** if you lack licenses/hardware [VMware+1](https://www.vmware.com/resources/hands-on-labs?utm_source=chatgpt.com)

### Week 2: Storage design

- 2 datastores/pools: `fast` (runtime) + `backup` (repository)
- Capacity plan + alert thresholds (80%/90%)

### Week 3: Backup policy + automation

- Schedule + retention + verification method
- Implement with your tool of choice (PBS/Nakivo/Veeam/etc.)

### Week 4: Recovery drills (3 scenarios)

- File restore, full VM restore, fastest restore method available
- Write restore report with achieved RTO/RPO

**Deliverables:** backup policy + restore runbook + restore report (timestamps + evidence).

---

# Month 3 — “Infra as code” on-prem: Ansible + templates + standards

**Goal:** new VMs become **consistent** and **secure** with minimal manual steps.

### Week 1

- Standard baseline role(s): users/groups, updates, SSH/RDP hardening, logging, time sync

### Week 2

- VM build flow: template + cloud-init/sysprep + post-config with Ansible

### Week 3

- Service onboarding checklist (what every new server must have)

### Week 4

- “Drift control” day: re-run automation, detect differences, fix

**Deliverables:** Ansible roles + onboarding checklist + “how to add a server in 30 minutes”.

---

# Month 4 — Terraform foundations (cloud-agnostic mindset)

**Goal:** you can create a full environment from scratch, safely and repeatably.

### Week 1

- Terraform basics + state handling (local first, then remote)

### Week 2

- Network as code: VPC/VNet + subnets + routes + security controls

### Week 3

- IAM/RBAC minimal privilege patterns

### Week 4

- “Destroy & rebuild” drill + documentation

**Labs:** KodeKloud hands-on practice is perfect for this style [kodekloud.com+1](https://kodekloud.com/?utm_source=chatgpt.com)

---

# Month 5 — Cloud core (pick a primary: AWS *or* Azure; touch the other lightly)

**Goal:** credible “cloud sysadmin / platform” baseline.

### AWS track (primary)

- Use AWS Skill Builder courses/labs [skillbuilder.aws+2Amazon Web Services, Inc.+2](https://skillbuilder.aws/?utm_source=chatgpt.com)
    
    Weeks: IAM basics → networking → compute → storage → monitoring
    

### Azure track (alternative primary)

- Microsoft Learn modules + Azure Sandbox [Microsoft Learn+1](https://learn.microsoft.com/en-us/training/support/use-your-own-subscription?utm_source=chatgpt.com)
    
    Weeks: identity/RBAC → networking → compute → storage → monitoring
    

**Deliverables:** “landing zone lite” (network + IAM/RBAC + logging) + cost notes.

---

# Month 6 — CI/CD + GitOps habits (what makes you “platform-ready”)

**Goal:** changes are tested, reviewed, and deployed predictably.

### Week 1

- Pick pipeline tool (GitHub Actions / GitLab CI)
- Build: lint + basic tests + artifact build

### Week 2

- Pipeline deploy to a lab environment (VM or container)

### Week 3

- Secrets handling + environment separation (dev/test/prod mindset)

### Week 4

- Rollback + versioning + release notes template

**Deliverables:** pipeline repo + runbook “how deployments work” + rollback procedure.

---

# Month 7 — Containers + Kubernetes fundamentals (hands-on labs)

**Goal:** you can run and debug workloads on K8s.

### Week 1–2

- Core objects: Pods, Deployments, Services, Ingress
- Labs: KubeAcademy + KodeKloud [kube.academy+1](https://kube.academy/?utm_source=chatgpt.com)

### Week 3

- ConfigMaps/Secrets + health checks + autoscaling basics

### Week 4

- Troubleshooting drills (crashloop, DNS, image pull, networking)

**Deliverables:** K8s “starter platform” + troubleshooting cheat sheet.

---

# Month 8 — Kubernetes operations (the “hire me” layer)

**Goal:** you can operate a cluster like an SRE-lite.

### Week 1

- Ingress + certificates (renewal plan)

### Week 2

- Storage classes + backups for workloads (concept + implementation)

### Week 3

- Cluster upgrades: plan + staging + rollback strategy

### Week 4

- RBAC + admission controls basics (safe defaults)

**Deliverables:** ops runbook + upgrade runbook + “day-2 operations” checklist.

---

# Month 9 — Observability (metrics/logs/traces) + incident workflow

**Goal:** you detect issues early and resolve fast.

### Week 1

- Metrics baseline (Prometheus/Grafana or equivalent)

### Week 2

- Central logs (Elastic fits your current stack)

### Week 3

- Tracing basics (OpenTelemetry concepts)

### Week 4

- On-call simulation: 3 alerts → triage → root cause → fix → postmortem

**Deliverables:** dashboards + alert rules + postmortem template + 1 real incident report (from a drill).

---

# Month 10 — Security engineering for sysadmins (defensive, practical)

**Goal:** harden systems and reduce blast radius, without becoming “SOC-only”.

### Week 1

- Identity security: MFA everywhere possible, conditional access patterns

### Week 2

- Secrets management approach (vaulted secrets, rotation notes)

### Week 3

- Endpoint hardening baseline (Windows + Linux servers) + audit logging

### Week 4

- Attack-surface review + remediation sprint
    
    Optional gamified practice: TryHackMe / HTB Academy paths (choose defensive/infra modules) [TryHackMe+1](https://tryhackme.com/paths?utm_source=chatgpt.com)
    

**Deliverables:** hardening checklist + “security baseline” Ansible role + logging coverage document.

---

# Month 11 — Reliability engineering + DR (gamedays)

**Goal:** you can keep services available and recover under pressure.

### Week 1

- Define SLOs (simple): availability + latency or error rate

### Week 2

- Chaos drills: DNS failure, cert expired, disk full, node down

### Week 3

- DR drill: restore critical service end-to-end (not just VM)

### Week 4

- Cost/performance review: right-sizing + storage retention tuning

**Deliverables:** SLO doc + gameday reports + DR report with achieved RTO/RPO.

---

# Month 12 — Capstone: “Mini-platform” (hybrid, production-style)

**Goal:** one coherent project that proves you’re “AI-proof”.

Capstone build (end-to-end):

- Terraform deploy (cloud landing zone lite)
- App/workload on Kubernetes
- Identity/RBAC
- Observability (metrics + logs + alerts)
- Backups + restore test
- Runbooks + diagrams + demo video (optional)

**Deliverables:** one polished repo + architecture PDF + runbooks + evidence pack.
