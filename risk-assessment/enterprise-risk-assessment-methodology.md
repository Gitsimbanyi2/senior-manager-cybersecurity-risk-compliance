# Enterprise Risk Assessment Methodology

## Purpose

Define a repeatable approach for identifying, analyzing, evaluating, and treating information security risks across the organization.

## Scope

- Information assets (data, applications, infrastructure, people)
- Business processes supporting critical operations
- Third-party and supply chain dependencies

## Assessment Process

### 1. Asset Identification

Catalog critical assets including:

- Core banking / financial systems
- Customer data repositories
- Network infrastructure and cloud services
- Identity and access management systems

### 2. Threat Identification

| Threat Category | Examples |
|-----------------|----------|
| External | Ransomware, phishing, DDoS, credential theft |
| Internal | Privileged abuse, data exfiltration, misconfiguration |
| Environmental | Power failure, natural disaster, hardware failure |

### 3. Vulnerability Assessment

- Automated vulnerability scanning
- Configuration review against CIS benchmarks
- Penetration testing (internal and external)
- Code and application security review

### 4. Risk Analysis

**Risk Score = Likelihood × Impact**

| Level | Score | Action |
|-------|-------|--------|
| Critical | 20–25 | Immediate remediation, executive escalation |
| High | 15–19 | Remediation within 30 days |
| Medium | 8–14 | Remediation within 90 days |
| Low | 1–7 | Accept or monitor |

### 5. Risk Treatment Options

- **Mitigate** — Implement controls to reduce likelihood or impact
- **Transfer** — Insurance or contractual liability shift
- **Accept** — Documented acceptance with management approval
- **Avoid** — Discontinue the risky activity or system

### 6. Reporting

Deliverables include:

- Executive risk summary dashboard
- Detailed risk register with owners and deadlines
- Trend analysis (quarterly)
- Board-level cyber risk briefing

## Review Cycle

- Full assessment: Annually
- Targeted reassessment: After major changes or incidents
- Continuous monitoring: Ongoing via SOC and GRC tools
