# Sigma Rule: Dolphin Loader Detection via LOLBin Execution

This repository provides a Sigma rule designed to detect execution behaviors associated with *Dolphin Loader* malware. It specifically targets the misuse of native Windows binaries to run payloads — a common technique employed by modern loaders.

## Summary

Dolphin Loader is a malware-as-a-service loader that abuses legitimate Windows tools like ⁠ regsvr32 ⁠, ⁠ rundll32 ⁠, and ⁠ mshta ⁠ to download or execute second-stage payloads. It is known for deploying infostealers and remote access trojans through phishing and cracked software channels.

## Rule File

•⁠  ⁠[rules/win_dolphinloader_lolbin_detect.yml](rules/win_dolphinloader_lolbin_detect.yml)

## Detection Strategy

This rule matches:
•⁠  ⁠Suspicious command-line usage of LOLBins
•⁠  ⁠Executed from ⁠ cmd.exe ⁠ or ⁠ powershell.exe ⁠
•⁠  ⁠Behavior typically seen during initial infection

## Usage

You can deploy this rule in any Sigma-compatible SIEM like Splunk, Elastic SIEM, or Sentinel with a proper backend translation.
