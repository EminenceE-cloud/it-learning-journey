
# Security Incident Investigation: Anonymous IP Address

## 1. Project Overview

This project documents an investigation of an anonymous IP address alert involving one user in a Microsoft Defender training environment.

The investigation followed a security operations runbook and used Microsoft Defender, Microsoft Entra sign-in logs, and VirusTotal IP reputation information.

**Environment:** Authorised training lab  
**Investigation type:** Identity and sign-in investigation  
**Platform:** Microsoft Defender and Microsoft Entra ID  
**Status:** Investigation completed; final disposition inconclusive  
**Focus:** SOC investigation, authentication analysis, alert correlation, and incident documentation

> All findings are based on a training environment. Sensitive account identifiers and IP addresses have been excluded.

## 2. Incident Summary

An alert identified anonymous IP address activity involving one user. The reported first and last activity was September 23, 2026, at 10:49.

During the investigation, approximately six related alerts were identified between 10:36 and 10:49. The alerts involved the same user, source IP address, and reported location.

The source IP was identified by VirusTotal as associated with a VPN. The reported geographic location differed from the user's usual sign-in locations.

A successful sign-in was observed, MFA was satisfied, and the device was marked as unmanaged.

## 3. Investigation Objectives

- Verify the affected user account.
- Investigate the source IP address and its reputation.
- Determine whether VPN or privacy-relay usage could explain the activity.
- Compare the sign-in client with historical activity.
- Identify other users or correlated alerts associated with the source.
- Review authentication, device, mailbox, URL, and phishing indicators.
- Determine whether alert tuning was justified.
- Document the findings and outstanding investigation gaps.

## 4. Investigation Findings

| Runbook question | Finding |
|---|---|
| 1. Was the user verified? | Yes |
| 2. Could the source IP be investigated? | Yes |
| 3. Was VPN/iCloud Private Relay confirmed for the user? | Unknown |
| 4. Was the user-agent different from historical activity? | No |
| 5. Did other users authenticate from the same IP? | No |
| 6. Had the user previously signed in from this location? | No |
| 7a. Was there a successful sign-in? | Yes |
| 7b. Was MFA satisfied? | Yes |
| 7c. Was the device managed? | No |
| 8. Did the activity occur during business hours? | No |
| 9. Were correlated events found? | Yes — approximately six alerts |
| 10. Was alert tuning necessary at this stage? | No |
| 11. Was the source IP known to be malicious? | No known malicious reputation identified |
| 12. Were mailbox manipulation indicators found? | No |
| 13. Was known malicious URL access identified? | No |
| 14. Were other suspicious sign-ins identified? | No |
| 15. Were phishing-email alerts identified? | No |

**Evidence limitation:** A finding of "No" means that the relevant activity was not identified in the data reviewed. It does not establish that the activity never occurred, particularly where telemetry coverage or log availability has not been confirmed.

## 5. Detailed Evidence and Analysis

### Source IP and reputation

A one-month sign-in log review identified successful sign-ins from the source IP on the incident date, but no matching sign-ins before or after that date within the reviewed period.

VirusTotal indicated that the IP was associated with a VPN. No known malicious reputation was identified during the investigation.

**Assessment:** VPN use is plausible, but the evidence does not confirm that the user intentionally used a VPN or establish that the IP was safe.

### Authentication and device

A successful sign-in was observed, and MFA was satisfied. The device was marked as unmanaged.

The reported browser and operating system were Microsoft Edge and Windows 10, consistent with the user's historical client information.

**Assessment:** MFA and familiar client characteristics are relevant evidence, but neither rules out compromised credentials, session abuse, or unauthorised access from an unmanaged device.

### Location and timing

The sign-in location differed from the user's usual locations, and no previous sign-ins from the reported location were identified in the reviewed period. The activity was assessed as occurring outside business hours.

**Assessment:** The unfamiliar location and timing increase the need for validation. VPNs can affect apparent geolocation, so the reported location does not establish the user's physical location.

### Correlated alerts

Approximately six alerts were identified between 10:36 and 10:49. The alerts involved the same user, source IP, and reported location.

**Assessment:** These events should be reviewed individually to establish whether they represent separate suspicious activities or multiple detections of one sequence. Their number alone does not prove an attack.

### Additional checks

No mailbox manipulation, known malicious URL access, other suspicious sign-in attempts, or phishing-email alerts were identified in the reviewed data.

**Assessment:** These checks did not provide additional evidence of compromise. The conclusions remain subject to the available telemetry and review scope.

## 6. Risk Assessment

**Preliminary outcome:** Suspicious activity requiring further validation.

The investigation identified several risk indicators:

- Anonymous or VPN-associated source IP.
- Unfamiliar geographic location.
- Successful authentication from an unmanaged device.
- Activity outside business hours.
- Multiple related alerts within a short period.

Potentially reassuring findings included satisfied MFA, a familiar browser and operating system, and no additional indicators identified in the reviewed sources.

These findings do not conclusively establish either legitimate activity or account compromise.

## 7. Alert Tuning Decision

Alert tuning was not recommended at this stage.

The source IP's VPN association, unfamiliar location, unmanaged device, and correlated alerts have not been sufficiently explained. Changing detection logic or adding an IP exclusion could suppress future detections of legitimate threats.

Any future tuning should require validated benign activity, documented justification, and appropriate approval.

## 8. Recommended Follow-up Actions

1. Validate the activity with the account owner or an authorised lab administrator, if the lab scenario permits.
2. Review all six alerts, including their titles, severity, evidence, timestamps, and relationships.
3. Examine sign-in details for authentication methods, Conditional Access results, device identifiers, and session context.
4. Confirm whether the reported IP belongs to a known VPN service and whether the user had a legitimate reason to use it.
5. Review available audit records for suspicious account changes, new authentication methods, session activity, or other post-sign-in actions.
6. Preserve relevant evidence and escalate according to the applicable incident-response procedure if compromise becomes more likely.
7. Perform containment only when justified by the evidence and permitted by the lab procedure.

No containment action is claimed to have been performed during this investigation.

## 9. Conclusion

This investigation demonstrated a structured approach to reviewing an anonymous-IP alert using authentication evidence, IP reputation information, device context, correlated alerts, and additional security checks.

The combination of an unfamiliar location, VPN-associated IP, unmanaged device, unusual timing, and multiple related alerts justified continued scrutiny. However, the evidence gathered was insufficient to confirm account compromise or determine that the activity was legitimate.

The appropriate disposition is **inconclusive — further validation required**.

## 10. Skills Practised

- Microsoft Defender incident investigation
- Microsoft Entra sign-in log analysis
- IP reputation assessment
- Authentication and MFA analysis
- Device-management context review
- Alert correlation and triage
- Runbook-driven investigation
- Incident reporting and evidence-based conclusions
- Security alert tuning considerations

## 11. Learning Outcome

This exercise reinforced the importance of correlating multiple indicators, distinguishing evidence from assumptions, documenting investigation limitations, and avoiding premature conclusions during security incident triage.

## Disclaimer

This is a training-lab case study. It documents the investigation performed in an educational environment and does not represent production incident-response experience.
