# Lessons Learned & Analyst Reflection

## Gaps Identified
- Lack of immediate automated perimeter blocking allowed over 400 failed attempts before analyst intervention.
- Internal service accounts lacked distinct alerting thresholds compared to standard end-user accounts.

## Tuning & Detection Improvements
- **Splunk Alert Logic:** Implement automated trigger:
  `index=windows EventCode=4625 | stats dc(Target_AccountName) as TargetCount count by Source_IP | where count > 50 AND TargetCount >= 5`
- Introduce active firewall API integration (SOAR) to auto-block IPs exceeding threshold limits.
