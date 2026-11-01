VirusTotal Analysis

1. Objective

The objective of this investigation is to examine the suspicious domain and URL identified during email header and initial triage analysis.

VirusTotal was used to review security vendor detections and available reputation information.

2. Domain Analysis

Indicator:'yznphish.com'

VirusTotal result: 0/92 detections

- No security vendors flagged the domain as malicious.
- The domain's last analysis was approximately 15 days before the screenshot was captured.
- Some vendors were marked as unrated.

Finding: No malicious detections were reported in the available analysis. However, this does not establish that the domain is safe.
<img width="957" height="506" alt="Screenshot 2026-10-30 200535" src="https://github.com/user-attachments/assets/4543a149-6486-4f56-a08a-0f7735fa5897" />

3. URL Analysis

Indicator: 'https://yznphish.com/secure/login?ref=8834211'

VirusTotal result: 0/93 detections

- No security vendors flagged the URL as malicious.
- The report showed no status or content type.
- The associated domain was 'yznphish.com'.
- The report date displayed was 15 October 2026.

Finding: No malicious detections were reported for the URL in the available analysis.
<img width="958" height="512" alt="Screenshot 2026-11-01 195826" src="https://github.com/user-attachments/assets/0d07f708-fd31-472a-a4e9-9c6957a42a5f" />


4. HTML Destination Analysis

Indicator: 'yznphish.example.invalid'

VirusTotal result: No report confirmed.

VirusTotal did not return a matching report through the attempted search.

The .invalid domain ending is reserved for invalid example addresses. Therefore, this destination is treated as a training indicator rather than a functioning public website.
<img width="958" height="574" alt="image" src="https://github.com/user-attachments/assets/6f53d525-50ce-4dd7-b791-c9cbb0ddc8a0" />


5. Security Observations

Although VirusTotal returned zero detections for the first two indicators, the email remains suspicious because of other evidence:

1. The sender impersonates PayPal.
2. The sender and Reply-To addresses use unrelated suspicious-looking domains.
3. SPF authentication failed.
4. DKIM verification was reported as failed.
5. DMARC authentication was reported as failed.
6. The plain-text URL and HTML destination do not match.

A zero-detection result does not prove that an indicator is safe. Security vendor coverage and analysis dates must also be considered.

6. Evidence Limitations

This investigation uses a controlled training email.

The IP addresses and HTML destination are simulated or reserved example indicators. No real malicious infrastructure or live phishing activity has been established.

The VirusTotal results are based on the reports visible during this investigation and should not be treated as permanent reputation verdicts.

7. Preliminary Conclusion

VirusTotal did not identify the investigated domain or URL as malicious in the available reports.

However, the email contains multiple other suspicious characteristics and failed authentication checks.

The overall email verdict therefore remains Suspicious - likely phishing.
