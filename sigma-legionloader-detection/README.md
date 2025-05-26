# Sigma Rule: Legion Loader Detection via regasm and Process Hollowing

This Sigma rule detects the early-stage activity of **Legion Loader**, a malware that drops infostealers and RATs by abusing `regasm.exe` and executing hollowed payloads.

## Summary

*Legion Loader* is a multi-payload dropper using LOLBins like `regasm.exe` in stealthy mode (`--nologo`, `--silent`) to evade detection. It often sets up **process hollowing** immediately after execution.

## Detection Logic

This rule detects:
- `regasm.exe` executed with stealth flags
- Spawned from LOLBin-heavy attack chains (`cmd.exe`, `powershell.exe`)

## Rule Location

- [`rules/win_legionloader_regasm_hollowing_detect.yml`](rules/win_legionloader_regasm_hollowing_detect.yml)

## Notes

- Rule tuned for high fidelity by narrowing to rare command-line flags
- False positives are minimal on modern Windows environments
- Useful for detecting loaders prior to actual payload deployment
