# Linux Base64 Decoding Dataset

## Source

Splunk Attack Data

## MITRE ATT&CK

T1140 — Deobfuscate/Decode Files or Information

## Telemetry

Linux Auditd `EXECVE` events

## Source Type

`auditd`

## Dataset

`linux_auditd_base64.log`

## Description

This dataset contains Linux Auditd EXECVE records showing execution of the
`base64` utility with decoding options.

The dataset is used for a controlled SIEM investigation and detection
engineering exercise.

## Splunk Configuration

| Setting | Value |
|---|---|
| Index | `soc_lab` |
| Sourcetype | `auditd` |
| Host | `linux-lab` |

## Origin

The dataset originates from the Splunk Attack Data project and corresponds
to MITRE ATT&CK technique T1140.

## Disclaimer

This is security research / attack simulation data and should not be
interpreted as evidence of a real-world incident.
