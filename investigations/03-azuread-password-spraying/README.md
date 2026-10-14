# Investigation 03: Azure AD Password Spraying

## Objective

Investigate failed Azure AD sign-ins to identify whether a source
is attempting authentication against multiple accounts.

## Hypothesis

A source IP generating failures against many distinct accounts in
a short interval may indicate password spraying.

## Evidence

- 31 invalid-credential events
- 31 distinct accounts targeted
- Source IP: 82.1.1.35
- Observed duration: approximately 1.56 minutes
- Application: Azure Active Directory PowerShell
- No successful sign-ins observed in the searches performed

## Assessment

The observed pattern is consistent with attempted password spraying.
Account compromise has not been established.

See [report.md](report.md) for findings, limitations, and recommendations.

## Query Library

See [queries/splunk](queries/splunk/) for the SPL query files.

## Evidence Screenshots

Search-result screenshots belong in `screenshots/`.
