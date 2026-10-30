Email Authentication Analysis: SPF, DKIM and DMARC

1. Objective

The objective of this investigation is to examine the email's SPF, DKIM and DMARC authentication results to determine whether the sender was successfully authenticated.

2. Authentication Results

The supplied email contains the following results in its Authentication-Results header:

| Authentication | Result | Explanation |
|---|---|---|
| SPF | FAIL | The sending IP was not authorised according to the reported SPF check. |
| DKIM | FAIL | The reported DKIM signature verification failed. |
| DMARC | FAIL | Neither SPF nor DKIM passed with the required alignment. |

3. SPF Analysis

Reported result: spf=fail

- Envelope sender domain: 'yznphish.com'
- Reported sending IP: '203.0.113.77'

The receiving system reports that the sending IP failed the SPF check for the sender domain.

SPF checks whether a mail server is authorised to send emails on behalf of a domain. A failure can indicate that the sending server is not authorised.

4. DKIM Analysis

Reported result: 'dkim=fail'

- Reported signing domain: 'yznphish.com'
- Reported result: Signature did not verify.

DKIM uses a digital signature to help verify that an email was authorised by the signing domain and that signed content has not been altered.

The supplied email text does not show a 'DKIM-Signature' header. Therefore, the reported failure cannot be independently verified from the available sample.

5. DMARC Analysis

Reported result: 'dmarc=fail'

- Visible From domain: 'yznphish.com'
- Reported policy: 'p=REJECT'
- Reported disposition: 'dis=none'

DMARC checks whether SPF or DKIM passes and aligns with the domain shown in the visible From address.

Since both SPF and DKIM are reported as failed, DMARC also reports a failure.

The reported 'p=REJECT' indicates a policy requesting rejection of emails that fail DMARC. However, the sample reports 'dis=none', meaning no rejection disposition is recorded in this header. The reason for this difference cannot be established from the supplied evidence.

6. Security Findings

The email has several authentication concerns:

1. SPF authentication failed.
2. DKIM verification failed according to the supplied header.
3. DMARC authentication failed.
4. The visible sender impersonates PayPal while using the domain 'yznphish.com'.

These findings increase suspicion that the email is attempting sender impersonation.

7. Evidence Limitations

This is a controlled training sample. The authentication results are text contained in the supplied email and have not been independently verified against live DNS records or a trusted mail gateway.

The sample uses documentation-range IP addresses, so the reported sending infrastructure should not be treated as real-world infrastructure.

The absence of a visible DKIM-Signature header also prevents independent verification of the reported DKIM failure.

8. Preliminary Conclusion

The supplied authentication results indicate that the email failed SPF, DKIM and DMARC checks.

Combined with the suspicious sender domain and other findings from the initial triage, the email remains highly suspicious.

Further investigation will examine the URLs and domains using VirusTotal, without opening or visiting the suspicious links.
