# Custom Wazuh Rules

Place reviewed custom rule files in this directory.

- `local_rules.xml` should contain only the rule configuration actually tested by the team.
- Document the Wazuh version and test evidence in the pull request or commit message.
- Do not claim rule `100100` works until the five-failures-within-60-seconds scenario has been validated in the deployed environment.

If the team has not yet validated the rule, keep this README and add the actual rule file later. Do not upload a guessed or untested configuration as a completed detection.
