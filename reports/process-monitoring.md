# Incident Report: Process Monitoring with Sysmon

**Report ID:** IR-02  
**Status:** Draft — replace placeholders with observed results  
**Author:** [Member 2]  
**Reviewer:** [Member name]  
**Test date/time and timezone:** [YYYY-MM-DD HH:MM TZ]

## 1. Executive Summary

[Summarize whether Sysmon process-creation telemetry for Notepad was recorded locally and collected by Wazuh.]

## 2. Objective and Scope

Validate process-creation visibility for a benign application on the Windows lab endpoint using Sysmon Event ID 1.

## 3. Environment

- Endpoint OS/build: [version]
- Wazuh server version: [version]
- Wazuh agent version/status: [version/status]
- Sysmon version: [version]
- Sysmon configuration source/version: [source and commit/version]

## 4. Test Procedure

1. Confirm Sysmon is installed and running.
2. Confirm the Wazuh agent is configured to collect the Sysmon event channel.
3. Launch Notepad on the lab endpoint.
4. Locate Sysmon Event ID 1 in Event Viewer.
5. Search for the event in Wazuh and record whether it arrived.
6. Save sanitized evidence.

## 5. Expected Results

Sysmon records a process-creation event for Notepad. If the event channel is correctly configured for collection, the event should be available for review in Wazuh. A Wazuh alert is not guaranteed unless a matching rule generates one.

## 6. Actual Results

- Sysmon Event ID 1 found locally: [Yes/No]
- Notepad process identified: [Yes/No]
- Event received by Wazuh: [Yes/No]
- Alert generated: [Yes/No; include actual rule ID if applicable]
- Relevant timestamp: [timestamp]
- Notes: [details]

## 7. Evidence

- `../evidence/process-monitoring/[screenshot-or-log-name]`
- [Explain what the evidence proves.]

## 8. Analysis and Limitations

[Document collection configuration, filtering, delays, and whether the test proves local logging, forwarding, or alerting. These are separate outcomes.]

## 9. Conclusion

[State only the result supported by evidence.]

## 10. Review

- Peer reviewer: [name]
- Review date: [date]
- Issues corrected: [details]
