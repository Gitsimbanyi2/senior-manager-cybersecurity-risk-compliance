# Incident Response Playbook

## Phases (NIST SP 800-61)

### 1. Preparation

- Maintain IR plan, contact lists, and escalation matrix
- Ensure SIEM, EDR, and backup systems are operational
- Conduct tabletop exercises at least annually

### 2. Detection & Analysis

- Triage alerts from SIEM/SOC within defined SLA
- Classify incident severity (P1–P4)
- Preserve evidence: logs, disk images, network captures
- Determine scope: affected systems, data, and users

### 3. Containment

| Strategy | When to Use |
|----------|-------------|
| Short-term | Isolate affected host, disable compromised account |
| Long-term | Segment network, apply emergency patches, restrict access |

### 4. Eradication

- Remove malware, close attack vectors
- Reset credentials for compromised accounts
- Patch vulnerabilities exploited in the attack

### 5. Recovery

- Restore systems from clean backups
- Monitor restored systems for 72+ hours
- Validate integrity before returning to production

### 6. Lessons Learned

- Post-incident review within 5 business days
- Update detection rules and playbooks
- Report to management and regulators as required

## Severity Classification

| Priority | Criteria | Escalation |
|----------|----------|------------|
| P1 | Active breach, data exfiltration, ransomware | CISO, CEO, Legal, Regulator |
| P2 | Confirmed compromise, limited scope | CISO, IT Director |
| P3 | Suspicious activity under investigation | SOC Lead |
| P4 | Low-impact event, auto-resolved | SOC Analyst |

## Communication Templates

- **Internal notification** — IT leadership within 30 minutes (P1/P2)
- **Regulatory notification** — Per jurisdiction requirements (e.g., 72 hours GDPR)
- **Customer notification** — If personal data affected, per legal guidance
