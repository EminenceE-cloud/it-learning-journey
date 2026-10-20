# Windows Security Baseline Checks

## Project Overview

This project documents basic Windows security checks to develop practical skills in endpoint security and system administration.

**Project type:** Cybersecurity / Endpoint Security  
**Level:** Beginner  
**Environment:** Windows computer  
**Status:** Completed

## Objectives

- Check the Windows Firewall status.
- Review basic Windows security information.
- Understand why firewall protection and system updates matter.
- Record findings and identify areas that may require further investigation.

## Security Checks

| Check | Purpose |
|---|---|
| Windows Firewall | Review whether firewall protection is enabled. |
| Windows Security | Review the security status displayed by Windows. |
| Windows Update | Check whether updates are available. |
| Findings and documentation | Record observations without exposing sensitive information. |

## Practical Investigation

The checks below will be performed on a Windows computer. Results will be documented after each check.

### Check 1: Windows Firewall

Review the firewall status for the available network profiles.

### Check 2: Windows Security

Review the status of virus and threat protection and other available security features.

### Check 3: Windows Update

Review the update status and note whether Windows reports any pending updates.

## Results and Findings

### Check 1: Windows Firewall

**Result:** Windows Security reported that the firewall was on for the Domain, Private, and Public network profiles.

**Finding:** Firewall protection was enabled across the three displayed profiles at the time of inspection.

### Check 2: Virus & Threat Protection

**Result:** Windows Security displayed "No current threats."

**Finding:** No current threats were reported by the Windows Security interface during this check. This does not guarantee that the device is completely free of malware.

### Check 3: Windows Update

**Result:** Windows Update displayed an available Intel Extension driver update with a Download & install option.

**Finding:** A driver update was pending at the time of inspection. Its installation status and any effect on device security have not yet been verified.

## Overall Conclusion

The initial checks showed that Windows Firewall was enabled for all displayed network profiles and Windows Security reported no current threats. Windows Update also showed a pending Intel Extension driver update.

These observations provide a basic snapshot of the computer's security status. They do not constitute a complete security audit.

## Evidence and Learning

This practical exercise developed familiarity with:

- Windows Firewall network profiles
- Windows Security and threat-status reporting
- Windows Update and driver updates
- Recording system security observations accurately

All findings were recorded from the Windows interface during the practical checks.

## Security Considerations

- Do not disable Windows Firewall or antivirus protection to perform this project.
- Do not publish product keys, account details, device identifiers, or other sensitive information.
- A single security check does not establish that a computer is completely secure.
- Investigate warnings carefully before making configuration changes.

## Key Learning Objectives

- Understand basic endpoint security controls.
- Recognize the role of Windows Firewall and Windows Security.
- Practise documenting system security observations.
- Develop a repeatable approach to basic security reviews.
  

## Skills Demonstrated

- Windows administration fundamentals
- Endpoint security awareness
- Security status review
- Technical documentation
- Evidence-based reporting
