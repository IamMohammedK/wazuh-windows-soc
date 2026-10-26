# Evidence Guidelines

Store only sanitized evidence that supports a specific test result.

Recommended naming:
- `YYYY-MM-DD_failed-logon_event-4625.png`
- `YYYY-MM-DD_custom-rule-100100.png`
- `YYYY-MM-DD_sysmon_event-1_notepad.png`
- `YYYY-MM-DD_fim_file-modification.png`

For each image, note in the report:
1. What is shown.
2. Which claim it supports.
3. The relevant timestamp and timezone, if visible.
4. Whether the evidence is local to Windows or from Wazuh.

Before committing, redact passwords, tokens, enrollment secrets, personal data, public IPs, and real internal IPs/hostnames where sensitive. Never fabricate or edit evidence in a way that changes the meaning of the result.
