Email Header Analysis

Case Information

- Case ID: PHISH-2026-001
- Evidence: 'phishing_sample.eml.txt'
- Analysis Type: Static email-header review
- Status: Initial header analysis completed

1. Sender Information

| Header | Observed Value | Finding |
|---|---|---|
| From | security@yznphish.com | Does not match the claimed PayPal identity |
| Reply-To | recovery-support@paypal-account-help.ru | Different domain from the visible sender |
| Return-Path | bounce@mkt7.yznphish.com | Uses a separate subdomain |
| Message-ID | '<8f2c1a90-4e11-4c3a-9d2e-2b7c6a1f0033@mail.yznphish.com>' | Domain is consistent with the broader sender domain |
| X-Originating-IP | 192.0.2.201 | Documentation-range IP address |

2. Reported Received Chain

The sample contains the following reported hops:

1. '192.0.2.201' connected to 'smtp-relay9.mkt7.yznphish.com'.
2. 'smtp-relay9.mkt7.yznphish.com' reportedly connected to 'mx-in.example-corp.com' from '203.0.113.77'.
3. 'mx-in.example-corp.com' reportedly passed the message to 'mail.example-corp.com'.

These entries are observations from the supplied sample, not independently verified network events.

3. Authentication Results

The supplied 'Authentication-Results' header reports:

- SPF: fail
- DKIM: fail
- DMARC: fail

The 'Received-SPF' header also reports SPF failure for the sending IP '203.0.113.77'.

These results will be examined in detail in the next investigation stage. Because this is a synthetic sample, the results have not been independently verified against live DNS or a real mail system.

4. Suspicious Characteristics

- The claimed PayPal identity does not match the sender domain.
- The Reply-To address uses another domain.
- The Return-Path uses a separate subdomain.
- The sample reports failures for all three email authentication mechanisms.
- The reported sender IPs belong to documentation ranges.

5. Limitations

The email is explicitly labelled as a lab/training sample. Its domains and IP addresses cannot establish a real sender's identity or prove that the reported routing occurred.

No live mail-server logs or independent authentication records were supplied.

6. Preliminary Conclusion

The headers contain multiple indicators consistent with a simulated phishing email. The authentication results and URL indicators require further analysis before the investigation can be completed.

Next step: investigate SPF, DKIM and DMARC and distinguish the supplied header verdicts from independently verifiable results.
