# Sigma Rule: BabbleLoader Execution via LOLBins

This repository contains a Sigma rule for detecting BabbleLoader malware behavior using Windows process creation logs.

## Summary

BabbleLoader is a malware loader that utilizes native Windows binaries (⁠ regsvr32 ⁠, ⁠ mshta ⁠, ⁠ rundll32 ⁠) to evade endpoint protections. It has been observed deploying infostealers like WhiteSnake and Meduza through deceptive techniques.

## Detection Logic

The rule identifies suspicious parent-child process combinations involving LOLBins executed via command-line or PowerShell sessions — a known BabbleLoader tactic.

## Rule Location

•⁠  ⁠[⁠ rules/win_babbleloader_lolbin_detect.yml ⁠](rules/win_babbleloader_lolbin_detect.yml)

## Status

•⁠  ⁠Tested using simulated Windows logs (EventCode 4688)
•⁠  ⁠Low false positive profile in enterprise environments

## License

MIT
