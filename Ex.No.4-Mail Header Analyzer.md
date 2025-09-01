# Ex.No.4   MHA (Mail Header Analyzer)
## Aim :
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.
## Procedure
### Step 1: Get the Email Header
- First, you need to copy the full, raw header from the email.

- Gmail: Open the email, click the three dots (⋮), and select Show original.
<br>
<br>
<img width="1920" height="1080" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/03207d6d-2271-4bac-a442-1ddf2d079785" />

<br>
<br>


- Select all the text in the header and copy it.

<br>
<img width="1920" height="1080" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/fed77c87-3443-43d3-a8cf-54827df48f02" />

<br>
<br>

### Step 2: Use a Mail Header Analyzer (MHA)
- The easiest way to analyze the header is with an online tool.

- Navigate to a site like MXToolbox Email Header Analyzer.
 <br>
<br>

  <img width="1919" height="1053" alt="image" src="https://github.com/user-attachments/assets/43254222-09b5-4a21-9aae-6f1705bb23aa" />
<br>
<br>

- Paste the entire header you copied into the analysis box.
<br>
<br>

Click the "Analyze" button to get a parsed, easy-to-read report.
<br>
<br>

<img width="1920" height="1080" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/970658d9-350a-4124-8a65-badb3cc1f1f2" />


### Step 3: Analyze The Report
- This is the most critical step. In the analyzer's report, look for the SPF, DKIM, and DMARC results.
### Review the Overall Delivery Summary
- First, look at the high-level summary to get an immediate sense of the email's status.

- Check DMARC Compliance: The report shows the email is DMARC Compliant. This is the most important overall result.

- Check SPF Status: Both SPF Authenticated and SPF Alignment passed. This means the sending server was authorized.

- Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated failed (❌). This is a critical finding and indicates a problem with the email's digital signature.
<br>
<br>

<img width="1920" height="1080" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/de3cd5d2-0eaa-43de-8427-c5c99788c3f8" />

<br>
<br>

### Investigate the SPF Record and Email Path
- Next, verify why the SPF check passed.

- Examine the SPF Record: The SPF record for the domain is v=spf1 include:mailgun.org ~all. This record explicitly authorizes servers from Mailgun to send emails on its behalf.

- Trace the Relay Information: The delivery path shows the email was sent from m241-136.mailgun.net.

- Conclusion: Since the email came from a Mailgun server, which is authorized in the SPF record, the SPF check passed.
  <br>
  <br>
<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/581a4ba5-60a8-45db-a9a5-442b765c5e0e" />

<br>
<br>

### Analyze the DKIM Failure

<br>
<img width="1917" height="989" alt="image" src="https://github.com/user-attachments/assets/8c62253c-68c6-42cc-b30e-d5581f4494ab" />
