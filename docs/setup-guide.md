# Setup Guide (Working Checklist)

> Record the exact versions, dates, and configuration used by your team. Do not paste secrets into this file.

## 1. Prepare Virtual Machines

- [ ] Install VirtualBox.
- [ ] Create Ubuntu Server **24.04 LTS** VM (suggested: 4 vCPU, 8 GB RAM, 50 GB disk).
- [ ] Create Windows 10/11 VM (suggested: 2–4 vCPU, 4 GB RAM, 40 GB disk).
- [ ] During VM creation, select **Skip Unattended Installation** if required by the team's workflow.
- [ ] Choose and document a controlled lab network. Bridged networking exposes VMs to the physical network; use it only when appropriate and authorized.
- [ ] Record sanitized VM details and take a baseline snapshot.

## 2. Install Wazuh

- [ ] Install the Wazuh all-in-one deployment on Ubuntu using the official instructions for the selected version.
- [ ] Record Wazuh version and installation date.
- [ ] Confirm the dashboard loads and sign-in works.
- [ ] Store credentials securely outside the repository.

## 3. Enroll Windows Agent

- [ ] Install the Wazuh agent version compatible with the server.
- [ ] Configure the server address and enrollment settings.
- [ ] Confirm the agent appears as active in the dashboard.
- [ ] On Windows, verify the service name before restarting it:

  ```powershell
  Get-Service *wazuh*
  ```

- [ ] Take a snapshot after the agent is connected and validated.

## 4. Configure Sysmon

- [ ] Install Sysmon using a reviewed configuration (for example, SwiftOnSecurity's configuration).
- [ ] Verify Sysmon is running and writing events.
- [ ] Configure the Wazuh agent to collect the Sysmon event channel according to the installed Wazuh version's documentation.
- [ ] Launch Notepad and verify Sysmon Event ID 1 exists.
- [ ] Verify the event is searchable on the Wazuh side before claiming end-to-end collection.

## 5. Validate Failed Logons

- [ ] Use only a dedicated lab test account, such as `SOC-Test`.
- [ ] Perform controlled failed-logon attempts.
- [ ] Verify Windows Security Event ID 4625.
- [ ] Inspect the Wazuh alert and confirm which rule ID actually matched. The project plan references rule 60122; verify this in the installed rule set.
- [ ] Implement and test custom rule ID 100100 for five failures within 60 seconds. Confirm the grouping/frequency logic matches the intended test.
- [ ] Save sanitized evidence.

## 6. Validate FIM

- [ ] Configure a dedicated test directory for monitoring.
- [ ] Create a test file, modify it, and delete it.
- [ ] Review Wazuh FIM events.
- [ ] Save sanitized evidence and note any delay or missed event.

## 7. Snapshots and Reporting

- [ ] Snapshot both VMs after phase 4.
- [ ] Snapshot both VMs after phase 7.
- [ ] Complete all three report templates.
- [ ] Have a teammate review each report.
- [ ] Remove secrets and sensitive network details before publishing.
