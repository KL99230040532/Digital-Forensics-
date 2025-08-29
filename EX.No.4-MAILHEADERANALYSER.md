# Ex.No.4   MHA (Mail Header Analyzer)
## Aim :
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.
## Procedure
### Step 1: Get the Email Header
- First, you need to copy the full, raw header from the email.

- Gmail: Open the email, click the three dots (⋮), and select Show original.
<br>
<br>
<img width="1838" height="884" alt="image" src="https://github.com/user-attachments/assets/59c07b22-a8f2-4e15-a518-43f4d856369a" />

<br>
<br>


- Select all the text in the header and copy it.

<br>
<img width="1505" height="873" alt="image" src="https://github.com/user-attachments/assets/9b36c7f4-0340-4176-9e3f-aff1731f5162" />

<br>
<br>

### Step 2: Use a Mail Header Analyzer (MHA)
- The easiest way to analyze the header is with an online tool.

- Navigate to a site like MXToolbox Email Header Analyzer.
 <br>
<br>

  <img width="1919" height="920" alt="image" src="https://github.com/user-attachments/assets/104fe018-c6d7-40e4-be98-4848a6b1b177" />

<br>
<br>

- Paste the entire header you copied into the analysis box.
<br>
<br>

Click the "Analyze" button to get a parsed, easy-to-read report.
<br>
<br>

<img width="1917" height="877" alt="image" src="https://github.com/user-attachments/assets/af5f17b5-0cfa-4a8c-b36d-929e32a6b8c6" />

### Step 3: Analyze The Report
- This is the most critical step. In the analyzer's report, look for the SPF, DKIM, and DMARC results.
### Review the Overall Delivery Summary
- First, look at the high-level summary to get an immediate sense of the email's status.

- Check DMARC Compliance: The report shows the email is DMARC Compliant. This is the most important overall result.

- Check SPF Status: Both SPF Authenticated and SPF Alignment passed. This means the sending server was authorized.

- Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated failed (❌). This is a critical finding and indicates a problem with the email's digital signature.
<br>
<br>
<img width="1907" height="863" alt="image" src="https://github.com/user-attachments/assets/869034eb-60a2-4b4d-b61b-714862cbf0f3" />

<br>
<br>

### Investigate the SPF Record and Email Path
- Next, verify why the SPF check passed.

- Examine the SPF Record: The SPF record for the domain is v=spf1 include:mailgun.org ~all. This record explicitly authorizes servers from Mailgun to send emails on its behalf.

- Trace the Relay Information: The delivery path shows the email was sent from m241-136.mailgun.net.

- Conclusion: Since the email came from a Mailgun server, which is authorized in the SPF record, the SPF check passed.
  <br>
  <br>
<img width="1917" height="874" alt="image" src="https://github.com/user-attachments/assets/9d3277b3-89e8-423a-a351-095dcef1f0a6" />
<br>
<br>

### Analyze the DKIM Failure

<br>
<img width="1885" height="786" alt="image" src="https://github.com/user-attachments/assets/c1d13cf5-5ccf-4e59-8ca2-7a252dc37c77" />
