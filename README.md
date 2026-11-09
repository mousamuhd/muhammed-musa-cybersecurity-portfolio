# Project 05 – Password Hash Security Auditing with Hashcat

**Status:** Controlled lab exercise; sample hashes and wordlist recorded  
**Tool:** Hashcat  
**Environment:** Kali Linux, local lab files  
**Hash mode:** MD5 (`-m 0`)

## 1. Objective

Understand how password hashes can be tested against candidate passwords in a controlled environment and why weak or reused passwords create security risk.

## 2. Scope and authorization

This exercise used sample test data created for the lab. Do not use password-cracking tools against accounts, hashes or systems without explicit authorization. Do not publish real password hashes or recovered credentials.

## 3. Lab setup recorded

A working directory was created:

```bash
mkdir -p ~/hash-lab
cd ~/hash-lab
```

The sample password file contained:

```text
password123
admin123
welcome123
```

The recorded `hashes.txt` entries were:

```text
482c811da5d5b4bc6d497ffa98491e38
0192023a7bbd73250516f069df18b500
5858ea228cc2edf88721699b2c8638e5
```

The wordlist contained:

```text
123456
qwerty
password
admin
password123
letmein
admin123
welcome123
```

These are lab sample values, not real user credentials.

## 4. Command used

The recorded Hashcat command was:

```bash
hashcat -m 0 hashes.txt wordlist.txt
```

The lab notes show Hashcat v7.1.2 starting and reporting CPU device information.

## 5. Results and interpretation

The available record confirms that Hashcat was launched against the sample MD5 hashes and wordlist. It does **not** preserve the final completion summary or recovered-password output. Therefore, this portfolio does not claim that all hashes—or any specific number of hashes—were successfully cracked.

To complete the result section, rerun the lab or retrieve the original terminal output and record:

| Metric | Actual result |
|---|---|
| Hashes tested | [Add count from file] |
| Hashes recovered | [Add actual Hashcat result] |
| Runtime | [Add actual runtime] |
| Hash mode | MD5 (`-m 0`) |
| Wordlist | Local sample wordlist |
| Tool version | Hashcat v7.1.2, as shown in recorded startup output |

## 6. Security significance

MD5 is a fast, legacy hashing algorithm and is not suitable for storing passwords. Password storage should use a purpose-built password-hashing scheme with salts and configurable work factors, such as Argon2id, scrypt, bcrypt or PBKDF2, according to current organizational requirements.

Defensive measures include:

- Use a modern password-hashing algorithm with unique salts.
- Encourage long, unique passwords and password-manager use.
- Enable multi-factor authentication.
- Monitor for credential stuffing and suspicious authentication activity.
- Apply rate limiting and breached-password screening where appropriate.

## 7. Evidence to add

- `evidence/hashcat-command-and-startup.png`
- `evidence/hashcat-final-summary.png`
- `evidence/lab-files-redacted.txt`

The original notes include the command and startup output, but the final result was not retained. Add the final summary only if it can be verified.

## 8. Learning outcome

This exercise developed familiarity with MD5 hash-mode selection, wordlist-based auditing and interpreting Hashcat startup output. It also reinforced the risks of weak passwords and fast legacy hashing algorithms.

## 9. Limitations

This was a local educational password-auditing exercise using sample data. It was not an attempt to access real accounts or recover another person's credentials.
