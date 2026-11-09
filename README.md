# Project 01 – Network Reconnaissance and Service Enumeration with Nmap

**Status:** Practical lab exercise completed  
**Tools:** Kali Linux, Nmap, VirtualBox  
**Environment:** Controlled VirtualBox lab; target recorded as `192.168.56.102`

## 1. Objective

Practise identifying a lab host, discovering exposed network ports and services, and interpreting the results as an initial step in a vulnerability assessment.

## 2. Scope and authorization

The scan was performed against a private IP address in a VirtualBox learning environment. This documentation is limited to that controlled lab. Do not scan networks or devices without explicit authorization.

## 3. Method

The lab workflow involved:

1. Starting the Kali Linux testing VM and the intended lab target.
2. Confirming the target's lab IP address.
3. Running Nmap against `192.168.56.102`.
4. Reviewing host availability, open ports, service names and version information.
5. Recording observations for further security review.

Example command pattern for a repeatable lab run (confirm the target IP and authorization before executing):

```bash
nmap -sV -oN nmap-service-enumeration.txt 192.168.56.102
```

The command above is provided as a reproducible example. It should not be treated as a verbatim record of every command used in the original exercise.

## 4. Recorded observations

The recorded scan output identified the host as up and reported multiple exposed services. Services noted in the lab included:

- FTP – `vsftpd 2.3.4`
- SSH – `OpenSSH 4.7p1`
- Telnet
- SMTP – Postfix
- DNS – ISC BIND 9.4.2
- HTTP – Apache httpd 2.2.8
- Samba
- MySQL
- PostgreSQL

The lab notes also include a later scan in which FTP (`vsftpd 2.3.4`) was the service shown. Because the scan conditions and exact command options for that later result were not retained here, it is recorded separately rather than treated as proof that all other services were closed.

## 5. Security significance

Exposed services increase the system's attack surface. Older service versions may require additional investigation, but a version string alone does not prove that a system is exploitable. Each finding should be validated against the actual configuration, patch level and vendor advisories.

## 6. Defensive recommendations

- Disable services that are not required.
- Restrict administrative services to trusted management networks.
- Replace insecure protocols such as Telnet with secure alternatives where appropriate.
- Review service versions and apply supported security updates.
- Use host firewalls and network segmentation.
- Repeat scans after remediation and compare the results.

## 7. Evidence to add

The initial exercise was discussed and scan output was recorded, but no original screenshot or complete raw scan file is currently included in this repository. Add sanitized evidence when available:

- `evidence/nmap-scan-summary.png`
- `evidence/nmap-service-enumeration.txt`

Do not create or label a recreated output as an original screenshot.

## 8. Learning outcome

This exercise developed familiarity with host discovery, port and service enumeration, reading Nmap output, and explaining why exposed services should be reviewed.

## 9. Limitations

This was a learning exercise, not a full penetration test. No claim is made that every listed service was vulnerable or successfully exploited.
