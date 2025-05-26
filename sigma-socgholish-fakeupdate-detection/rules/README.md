# Sigma Rule: SocGholish FakeUpdate Initial Infection Detection

This Sigma rule detects the initial stage of a SocGholish malware infection, where a user is lured into executing a fake update from the browser — triggering PowerShell, WScript, MSHTA, or CMD.

## Summary

SocGholish (aka FakeUpdates) is a JavaScript-based loader that abuses social engineering by tricking users into downloading malicious updates. This detection focuses on browser processes launching script interpreters unexpectedly.

## Detection Logic

This rule matches:
•⁠  ⁠Parent process: Web browsers like ⁠ chrome.exe ⁠, ⁠ firefox.exe ⁠, ⁠ msedge.exe ⁠
•⁠  ⁠Child process: Script engines like ⁠ powershell.exe ⁠, ⁠ wscript.exe ⁠, ⁠ mshta.exe ⁠, ⁠ cmd.exe ⁠

## Rule File

•⁠  ⁠[⁠ rules/win_socgholish_browser_script_spawn_detect.yml ⁠](rules/win_socgholish_browser_script_spawn_detect.yml)

## Notes

•⁠  ⁠False positives are rare in most environments unless scripted browser automation is used.
•⁠  ⁠Rule is ideal for catching first-stage user execution behavior.
