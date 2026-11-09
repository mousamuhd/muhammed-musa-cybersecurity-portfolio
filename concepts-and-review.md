# Syslog and Rsyslog – Lab Notes

## Syslog

Syslog describes a common approach and protocol for recording and transporting event messages from operating systems and applications. Messages can include timestamps, host identifiers, application names, facilities, severities and event text, depending on implementation and configuration.

## Rsyslog

Rsyslog is a Syslog implementation commonly used on Linux systems. Depending on configuration, it can collect messages, filter them, write them to files, and forward them to another logging server.

## Review points for the lab

| Review item | Value to record |
|---|---|
| Distribution | [Verified distribution/version] |
| Rsyslog installed | [Yes / No / Not checked] |
| Rsyslog service state | [Copy actual service state] |
| Configuration file reviewed | [Exact path, if reviewed] |
| Local log destination | [Exact path, if verified] |
| Remote forwarding configured | [Yes / No / Not checked] |

Common configuration locations vary by distribution. Do not change a production logging configuration without authorization and a rollback plan.
