# Investigation 02 — Linux Base64 Decoding Activity

## 1. Investigation Overview

This investigation analyzes Linux Auditd telemetry ingested into Splunk
to identify Base64 decoding activity and assess whether the observed
behavior is potentially suspicious.

The investigation is mapped to MITRE ATT&CK technique:

**T1140 — Deobfuscate/Decode Files or Information**

---

## 2. Objective

Determine:

- Which commands were executed.
- Whether Base64 decoding occurred.
- What data was supplied to the decoder.
- Whether the observed activity can be classified as malicious.
- Whether the available telemetry provides sufficient context for attribution.

---

## 3. Dataset

| Field | Value |
|---|---|
| Dataset | `linux_auditd_base64.log` |
| Telemetry | Linux Auditd |
| Source type | `auditd` |
| Index | `soc_lab` |
| Host | `linux-lab` |
| MITRE ATT&CK | T1140 |

The dataset contains Linux Auditd `EXECVE` records representing
execution of the `base64` utility.

---

## 4. Data Onboarding

The dataset was uploaded into Splunk using:

```text
Source type: auditd
Host: linux-lab
Index: soc_lab
