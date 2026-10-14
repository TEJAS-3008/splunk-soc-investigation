# Incident Investigation: Suspected Azure AD Password Spraying

## 1. Executive Summary

Analysis of the indexed Azure AD sign-in dataset identified 31
failed authentication events associated with a single source IP,
82.1.1.35. The events targeted 31 distinct accounts over
approximately 1.56 minutes.

All observed events had result code 50126, indicating invalid
credentials. The observed pattern is consistent with an attempted
password-spraying attack.

No successful sign-ins were observed in the searches performed.
This does not establish that no successful authentication occurred
outside the available dataset or collection window.

## 2. Investigation Scope

- SIEM: Splunk Enterprise
- Index: soc_lab
- Event category: SignInLogs
- Source IP: 82.1.1.35
- Result code investigated: 50126
- Dataset: Azure AD sign-in JSON logs
- Investigation focus: Failed authentication across multiple accounts

## 3. Key Findings

### Finding 1: Authentication failures

The indexed dataset contained 31 events. All returned result code
50126 with an invalid-credentials description.

### Finding 2: Multiple accounts targeted

The source IP 82.1.1.35 generated 31 failed events against
31 distinct accounts.

### Finding 3: Concentrated activity

The first and last observed events for this source were approximately
1.56 minutes apart.

### Finding 4: Consistent client context

The events shared the application name Azure Active Directory
PowerShell, client application Mobile Apps and Desktop clients,
and a Windows PowerShell 5.1 user-agent string.

This may indicate a common client or script. PowerShell can also
be used legitimately, so this evidence is not proof of malicious intent.

### Finding 5: Conditional Access and risk fields

The 31 events recorded:
- Conditional Access status: notApplied
- Authentication requirement: singleFactorAuthentication
- Risk level during sign-in: none
- Risk detail: none

These values do not, by themselves, establish why Conditional Access
was not applied or prove that the activity was benign.

### Finding 6: Successful authentication

No successful sign-ins were observed in the searches performed
against the indexed dataset.

## 4. Assessment

Assessment: Suspected password-spraying attempt.

Confidence: High that the observed activity is suspicious; the
available logs do not prove the exact password used, the operator's
identity, or the operator's intent.

The main indicators are the single source IP, the rapid targeting
of many distinct accounts, and the consistent invalid-credential
results.

Account compromise has not been established.

## 5. Recommended Response

1. Validate the source IP and activity with the identity/security team.
2. Review the relevant Azure AD sign-in records and policy configuration.
3. Check for related authentication events outside this dataset and
   collection window, including successful sign-ins.
4. Review targeted accounts for unusual activity and other risk signals.
5. Apply approved identity-security controls if the activity is
   confirmed to be malicious.
6. Preserve relevant logs and document any response actions.

## 6. Limitations

- The analysis is based on the events indexed in soc_lab.
- The dataset contains only 31 events in the observed result summary.
- The logs do not reveal the exact password attempted.
- The reason Conditional Access was not applied is not established.
- No successful authentication was observed in the searches performed;
  this is not proof that success was impossible or absent elsewhere.
- Source-IP ownership and operator identity have not been independently
  verified.

## 7. Reproducibility

The SPL queries used during the investigation are stored under
queries/splunk/.

Screenshots of important search results are stored under screenshots/.

The findings should be reassessed if additional telemetry becomes available.
