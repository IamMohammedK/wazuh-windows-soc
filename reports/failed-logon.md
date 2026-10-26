# Incident Report: Failed Logon Detection

**Report ID:** IR-01  
**Status:** Draft — replace placeholders with observed results  
**Author:** [Member 1]  
**Reviewer:** [Member name]  
**Test date/time and timezone:** [YYYY-MM-DD HH:MM TZ]

## 1. Executive Summary

[Summarize the controlled failed-logon test, whether the expected event and alert were observed, and the outcome. Do not state that detection succeeded until evidence confirms it.]

## 2. Objective and Scope

Validate that failed logons on the Windows lab endpoint are recorded and that Wazuh can detect the intended repeated-failure pattern.

## 3. Environment

- Wazuh version: [version]
- Endpoint OS: [Windows 10/11 build]
- Agent status: [observed status]
- Test account: `SOC-Test` (lab account)
- Network: [sanitized lab network description]

## 4. Detection Logic

- Windows event: **4625** (failed logon)
- Wazuh rule reference in project plan: **60122** — confirm the actual matched rule in the installed environment.
- Custom rule target: **100100**, five failed logons within 60 seconds.
- Rule configuration/commit: [path or commit hash]

## 5. Test Procedure

1. Confirm the Windows agent is connected.
2. Confirm the test account and audit settings are configured for the lab.
3. Perform the planned, controlled failed-logon attempts against the lab test account.
4. Search Windows logs for Event ID 4625.
5. Search Wazuh alerts and record the actual rule ID, timestamp, and relevant fields.
6. Repeat under the documented threshold test for the custom rule.

## 6. Expected Results

- Windows records the failed-logon event.
- Wazuh receives the configured event source.
- The custom detection triggers when the implemented conditions are met.

## 7. Actual Results

- Event 4625 observed: [Yes/No]
- Event reached Wazuh: [Yes/No]
- Actual matched rule ID: [ID / no alert]
- Custom rule 100100 triggered: [Yes/No]
- Observed timestamps: [timestamps]
- Notes or deviations: [details]

## 8. Evidence

- `../evidence/failed-logon/[screenshot-or-log-name]`
- [Describe what each item demonstrates; redact sensitive details.]

## 9. Analysis and Limitations

[Explain whether the observed behavior met expectations. Include possible causes of missing alerts, such as agent collection configuration, audit policy, rule conditions, or timing.]

## 10. Conclusion

[State only what the test evidence supports.]

## 11. Review

- Peer reviewer: [name]
- Review date: [date]
- Issues corrected: [details]
