
# Windows Network Troubleshooting Case Study

## Project Overview

This project documents a structured approach to diagnosing common Windows network connectivity problems using built-in networking commands.

**Project type:** IT Support / Networking  
**Level:** Beginner  
**Tools:** Windows Command Prompt

## Objectives

- Understand basic network configuration.
- Practise checking connectivity to another host.
- Learn how to trace a network route.
- Document troubleshooting steps and findings.

## Tools and Commands

| Command | Purpose |
|---|---|
| `ipconfig` | Displays IP configuration details. |
| `ping` | Tests connectivity to a destination. |
| `tracert` | Traces the route packets take to a destination. |

## Troubleshooting Procedure

### Step 1: Inspect Network Configuration

Run:

```cmd
ipconfig
```

Review the network adapter, IPv4 address, subnet mask, and default gateway.

### Step 2: Test Connectivity

Run:

```cmd
ping 8.8.8.8
```

Review whether replies are received or packets are lost. A failed ping alone does not prove that the internet connection is unavailable, because some networks block ICMP traffic.

### Step 3: Test DNS Resolution

Run:

```cmd
ping google.com
```

Check whether the hostname resolves to an IP address and whether replies are received. A failure may have several causes, including DNS issues or blocked ping traffic.

### Step 4: Trace the Network Route

Run:

```cmd
tracert google.com
```

Review the route information and note any hops that time out. A timeout at an individual hop does not necessarily indicate a network fault.

## Results and Findings

**Status:** Pending practical testing.

Record the actual command output and findings after running the tests on a Windows computer. Do not assume a command succeeded or that a fault was identified before reviewing the results.

## Troubleshooting Notes

When investigating a connectivity issue:

1. Check the local IP configuration.
2. Confirm that the network adapter is connected.
3. Test connectivity to the default gateway when appropriate.
4. Compare connectivity by IP address and hostname.
5. Review route information if needed.
6. Record findings before recommending a resolution.

## Key Learning Points

- Networking commands provide useful diagnostic information.
- IP connectivity and DNS resolution are related but different.
- Timeouts can have multiple explanations and require careful interpretation.
- Clear documentation makes troubleshooting easier to review and repeat.

## Conclusion

This case study provides a repeatable starting point for Windows network troubleshooting. It will be updated with real test results, observations, and any verified resolution as practical testing is completed.
