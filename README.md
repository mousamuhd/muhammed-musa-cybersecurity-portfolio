# Project 06 – Linux Log Analysis and Security Monitoring

**Status:** Practical learning exercise  
**Tools used:** Linux terminal, `/var/log`, Syslog / Rsyslog  
**Activities confirmed:** Examining system logs and monitoring activities

## 1. Objective

Practise examining Linux system logs and understanding how logging services such as Syslog and Rsyslog support system monitoring and security investigations.

## 2. Scope and accuracy

This documentation is based on the activities confirmed for this lab: using the Linux terminal and `/var/log`, working with Syslog / Rsyslog concepts, and examining system logs and monitoring activities.

The exact Linux distribution, log files opened, commands executed, event timestamps, observed alerts and investigation results were not provided. They are therefore **not claimed as completed findings** in this document.

Commands below are examples for a repeatable practice session. They are not represented as a verbatim record of commands already executed.

## 3. Tools and concepts

- **Linux terminal:** Used to navigate the system and inspect log files.
- **`/var/log`:** Common Linux directory containing system and service log files. Exact file names vary by distribution and configuration.
- **Syslog:** A standard logging protocol and ecosystem used to collect and route log messages.
- **Rsyslog:** A commonly used Syslog implementation that can receive, process, filter and forward log messages.

## 4. Practical workflow

1. Identify the Linux distribution and available logging service.
2. Inspect the contents of `/var/log`.
3. Identify relevant system and authentication log files available on that system.
4. Review recent log entries and note timestamps, host/process names, severity or facility information where present.
5. Monitor a log file for new entries during normal, authorized activity.
6. Review the Syslog / Rsyslog service status and configuration, where access is permitted.
7. Record observations and distinguish normal system activity from events that may warrant further investigation.

## 5. Example commands for a repeatable lab

List available log files:

```bash
ls -lah /var/log
```

Inspect recent entries in a log file that exists on the system:

```bash
sudo tail -n 50 /var/log/syslog
```

On some Debian/Ubuntu systems, authentication events may be recorded in:

```bash
sudo tail -n 50 /var/log/auth.log
```

On some Red Hat-family systems, a different file such as `/var/log/secure` may be used:

```bash
sudo tail -n 50 /var/log/secure
```

Follow a log as new entries are written:

```bash
sudo tail -f /var/log/syslog
```

Search for selected authentication-related terms in a file that exists:

```bash
sudo grep -iE "failed|failure|invalid|accepted" /var/log/auth.log
```

Check whether Rsyslog is installed and running on a systemd-based distribution:

```bash
systemctl status rsyslog
```

Inspect recent journal events on a system using systemd:

```bash
sudo journalctl -n 50
```

**Important:** Paths and commands are distribution-dependent. Check which files and services exist on the lab machine before using them. `journalctl` reads the systemd journal; it is not itself a Syslog file.

## 6. What to examine in log entries

Record only what the log actually shows:

- Timestamp and timezone, if available.
- Hostname and process or service name.
- Event message and event type.
- Username or source address only when present and safe to retain.
- Whether the event was expected in the lab context.
- Whether additional evidence is needed before drawing a conclusion.

Repeated failed authentication messages, unexpected service restarts or unusual privilege-related events can justify further review. A single log line alone does not necessarily prove malicious activity.

## 7. Findings and observations

The confirmed activity is examination of system logs and monitoring activities using the Linux terminal, `/var/log`, and Syslog / Rsyslog.

No specific failed-login count, suspicious IP address, detected incident, alert, timestamp, or remediation outcome was supplied. This portfolio therefore does not claim that a security incident was detected.

Complete the table only from actual lab evidence:

| Observation to record | Actual lab result |
|---|---|
| Linux distribution and version | [Add verified value] |
| Logging service present | [Add verified value] |
| Log files examined | [List files actually opened] |
| Monitoring method | [Add command/tool actually used] |
| Notable event observed | [Describe exact log entry, if any] |
| Security interpretation | [Explain cautiously] |
| Follow-up action | [Add action actually taken] |

## 8. Security value and recommendations

Effective log monitoring helps administrators and security teams understand system activity, investigate operational problems and identify events that may require security review.

Recommended practices include:
- Enable and maintain appropriate system and authentication logging.
- Synchronize system clocks so event timelines are reliable.
- Restrict access to log files because they may contain sensitive information.
- Protect logs against unauthorized modification or deletion.
- Forward important logs to a central collection platform where appropriate.
- Establish retention periods based on organizational policy and legal requirements.
- Investigate patterns across multiple events instead of relying on a single entry.
- Avoid placing credentials, tokens or other secrets in logs.

## 9. Evidence to add

No screenshots or raw log exports were included in the information used to create this project. Add sanitized evidence only after capturing it from your own lab:

- `evidence/screenshots/var-log-directory.png`
- `evidence/screenshots/log-review-terminal.png`
- `evidence/screenshots/rsyslog-service-status.png`
- `findings/lab-observations.md`

Before publishing, redact usernames, public IP addresses, hostnames, email addresses, session identifiers, tokens and any other private information. Do not upload full raw logs from a personal or business device.

## 10. Learning outcome

This exercise provided practical exposure to examining Linux system logs and monitoring activity, while developing familiarity with `/var/log` and the role of Syslog / Rsyslog in log collection.

## 11. Limitations

This is an educational lab record, not a production SOC investigation or incident response engagement. The available information supports documenting log examination and monitoring practice, but does not support claims of detecting a confirmed attack, identifying an attacker, or remediating a security incident.
