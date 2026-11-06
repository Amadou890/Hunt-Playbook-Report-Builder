# 📋 Hunt Playbook & Report Builder

A browser tool that guides an analyst through a threat hunt or alert triage with a checklist, then turns the findings into a structured case report. 
Live demo: 
## Why I built it

Hunts and triage notes are often inconsistent: steps get skipped and reports leave out the escalation reasoning. This tool keeps the process repeatable and makes the report reflect what was actually done.

## How it works

1. **Playbook:** choose a technique, work through the checklist, copy the suggested Splunk queries, add notes per step, and tick any escalation indicators you find.
2. **Case details:** record the who, what, when, and where, the indicators of compromise, your classification, and your escalation decision with rationale.
3. **Report:** copy a Markdown case report. Only the steps you ticked are listed as performed, and unticked steps are listed as not performed. Indicators can be defanged automatically.

## Playbooks included

| Playbook | ATT&CK |
|:--|:--|
| Suspicious PowerShell | T1059.001 |
| Run key persistence | T1547.001 |
| C2 beaconing | T1071 |
| Event log cleared | T1070.001 |
| Lateral movement | T1021 |
| Phishing email triage | T1566.002 |

Each playbook has a hypothesis, data sources, ordered steps with example Splunk queries, escalation indicators, common false positives, and suggested actions.

## How to use it

- **Online:** open the live demo link above.
- **Locally:** download `index.html` and open it in any browser.
- Replace placeholders such as `<host>` in the queries, and confirm the index and field names for your environment (queries assume `index=wineventlog`).

## Limitations

- Playbooks are starting points based on common analyst practice, not a substitute for your organization's procedures.
- Escalation indicators prompt a decision. They do not make it.
- Nothing is saved. Copy the report before closing the page.
- The Splunk queries have not all been validated against real data. _[Update this line after you test them.]_

## Tech

A single HTML file with vanilla JavaScript. No frameworks, no build step, no network requests.

## License

MIT. See `LICENSE`.
