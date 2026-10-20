
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

### Test 1: IP Connectivity

**Command used:**

```cmd
ping 8.8.8.8
```

**Result:** Received replies from the destination.

**Finding:** The computer successfully reached the tested public IP address during the test.

### Test 2: DNS Resolution and Connectivity

**Command used:**

```cmd
ping google.com
```

**Result:** The hostname resolved to `172.217.20.78`, and replies were received.

**Finding:** DNS resolution and ICMP connectivity to the resolved destination worked during the test.

### Test 3: Route Tracing

**Command used:**

```cmd
tracert google.com
```

**Result:** The trace completed successfully in six hops.

**Observations:**
- Hop 1 responded at `192.168.0.1`, consistent with the local router.
- Hops 2–4 used private IP addresses in the `10.x.x.x` range.
- Hop 5 responded to two of three probes; one probe timed out.
- Hop 6 reached `172.217.20.78`, the destination shown by the trace.

**Finding:** The destination was reachable. The isolated timeout at hop 5 did not stop the trace, and there was no evidence from this test alone of a complete route failure.

## Overall Conclusion

The three diagnostic tests showed successful connectivity to the tested IP address and hostname, successful hostname resolution, and a completed route trace.

No connectivity fault was identified by these tests. This does not rule out intermittent issues or problems with other network services.

## Evidence and Learning

These tests provided practical experience with Windows Command Prompt and the following networking commands:

- `ipconfig` — inspecting local network configuration
- `ping` — testing destination connectivity
- `tracert` — examining the route to a destination

The results were recorded from actual command-line tests on a Windows computer.

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
