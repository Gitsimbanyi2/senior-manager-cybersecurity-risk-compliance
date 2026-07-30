# SOC Detection Rules Guide

## Purpose

Guidelines for developing, tuning, and maintaining SIEM detection rules in a Security Operations Center (SOC) environment.

## Rule Design Principles

1. **Reduce false positives** — Tune thresholds and add contextual filters
2. **Prioritize by impact** — Align severity with business risk
3. **Enable response** — Each alert should map to a playbook action
4. **Document clearly** — Every rule needs a description and MITRE ATT&CK mapping

## Rule Categories

### Fraud & Transaction Monitoring

Detect anomalous payment patterns:

- Multiple failed or delayed mobile money transactions within a short window
- Unusual transaction volumes from a single account or terminal
- After-hours high-value transfers

### Insider Threat & Privileged Activity

Monitor privileged and destructive actions:

- Sudo/root usage on production database servers
- DDL operations: DROP, DELETE, ALTER, TRUNCATE
- Bulk data extraction queries targeting customer or account fields
- Repeated privileged actions indicating possible abuse

### Authentication & Access

- Brute-force login attempts exceeding threshold
- Impossible travel / geolocation anomalies
- New admin account creation outside change window
- VPN connections from unauthorized regions

### Data Exfiltration

- Large outbound data transfers to unknown destinations
- USB device usage on restricted endpoints
- Cloud storage uploads from sensitive systems

## Severity Levels

| Level | Description | Response SLA |
|-------|-------------|--------------|
| 13–15 | Critical — active fraud or data breach indicators | 15 minutes |
| 10–12 | High — privileged abuse or exfiltration patterns | 1 hour |
| 7–9 | Medium — suspicious but unconfirmed activity | 4 hours |
| 1–6 | Low / Informational | Next business day |

## Example Rule Structure (Wazuh XML)

```xml
<rule id="110409" level="13" frequency="10" timeframe="60">
  <if_matched_sid>110408</if_matched_sid>
  <description>Multiple failed payment events detected — possible fraud burst</description>
  <group>soc,fraud_detection,critical,</group>
</rule>
```

## Tuning & Maintenance

- Review alert volume weekly; adjust frequency and timeframe parameters
- Validate rules against purple-team exercises
- Retire rules with sustained zero true-positive rate over 90 days
- Version-control all rule changes with change management approval
