# Phsihing-Email-Investigation

A simulated SOC investigation into a suspected phishing email reported by an employee.

## Scenario

An employee reports receiving a suspicious email requesting
them to verify their account through an embedded link.

## Objectives

- Analyze the complete email headers
- Investigate SPF(Sender Policy Framework), DKIM(DomainKeys Identified Mail) and DMARC(Domain-based Message Authentication, Reporting & Conformance).
- Identify suspicious URLs and domains
- Analyze indicators using VirusTotal
- Identify all recipients of the campaign
- Identify users who interacted with the link
- Determine the scope of the incident
- Recommend containment and remediation

## Tools

- Email Headers
- VirusTotal
- Microsoft 365 Message Trace
- PowerShell
- Git/GitHub

## Investigation

1. [Header Analysis](investigations/01-header-analysis.md)
2. [Email Authentication](investigations/02-email-authentication.md)
3. [URL Analysis](investigations/03-url-analysis.md)
4. [Message Trace](investigations/04-message-trace.md)
5. [User Impact](investigations/05-user-impact.md)

## Findings

TBD

## Response

TBD
