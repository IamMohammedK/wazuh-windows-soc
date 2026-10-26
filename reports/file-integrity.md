# Incident Report: File Integrity Monitoring (FIM)

**Report ID:** IR-03  
**Status:** Draft — replace placeholders with observed results  
**Author:** [Member 3]  
**Reviewer:** [Member name]  
**Test date/time and timezone:** [YYYY-MM-DD HH:MM TZ]

## 1. Executive Summary

[Summarize which file operations were detected by Wazuh FIM and whether the results matched expectations.]

## 2. Objective and Scope

Validate monitoring of file creation, modification, and deletion in a dedicated test directory on the Windows lab endpoint.

## 3. Environment

- Endpoint OS/build: [version]
- Wazuh server version: [version]
- Wazuh agent version/status: [version/status]
- Monitored test path: [sanitized path]
- FIM configuration: [where and how configured]

## 4. Test Procedure

1. Configure the dedicated test directory for FIM.
2. Confirm the agent is connected and configuration is applied.
3. Create a harmless test file.
4. Modify the file contents and save it.
5. Delete the test file.
6. Search the Wazuh dashboard for the corresponding FIM events.
7. Record event times and observed operation types.

## 5. Expected Results

Wazuh reports the supported changes for the configured monitored path. Exact event details depend on the FIM configuration and platform.

## 6. Actual Results

| Operation | Observed in Wazuh? | Timestamp | Evidence |
|---|---|---|---|
| File creation | [Yes/No] | [timestamp] | [evidence filename] |
| File modification | [Yes/No] | [timestamp] | [evidence filename] |
| File deletion | [Yes/No] | [timestamp] | [evidence filename] |

## 7. Evidence

- `../evidence/file-integrity/[screenshot-or-log-name]`
- [Describe the file and event shown; redact sensitive details.]

## 8. Analysis and Limitations

[Explain any missing events, scan intervals, path exclusions, or configuration issues. Do not claim full filesystem monitoring if only a test directory was monitored.]

## 9. Conclusion

[State which operations were detected and what remains unverified.]

## 10. Review

- Peer reviewer: [name]
- Review date: [date]
- Issues corrected: [details]
