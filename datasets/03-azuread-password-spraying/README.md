# Azure AD Password Spraying Dataset

## Purpose

Azure AD sign-in events used to investigate suspicious authentication
failures and possible password spraying.

## Source

Splunk Attack Data repository:
https://github.com/splunk/attack_data

Technique: MITRE ATT&CK T1110.003 — Password Spraying.

## Metadata

See `password_spraying_azuread.yml` for the source dataset metadata.

## Local Dataset File

Expected filename: `azuread_signin.log`

The raw dataset is kept locally and is not committed to this repository.

## Splunk Ingestion

1. Obtain the dataset from the source repository.
2. Upload the JSON logs to Splunk.
3. Use the `soc_lab` index for this portfolio investigation.
4. Verify JSON field extraction before running the SPL queries.
5. Follow the investigation in `../../investigations/03-azuread-password-spraying/`.
