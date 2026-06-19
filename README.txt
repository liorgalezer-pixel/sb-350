SB 350 APPLICATION FORM — SETUP GUIDE
======================================

The form uses EmailJS to send submissions by email — no server required.
Follow these steps once to configure it.

─────────────────────────────────────────
STEP 1 — Create a free EmailJS account
─────────────────────────────────────────
Go to: https://www.emailjs.com
Sign up for a free account (200 emails/month free).

─────────────────────────────────────────
STEP 2 — Add an Email Service
─────────────────────────────────────────
1. In the EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose Gmail, Outlook, or any provider you use
4. Follow the authorization steps
5. Note down the SERVICE ID (looks like "service_xxxxxxx")

─────────────────────────────────────────
STEP 3 — Create an Email Template
─────────────────────────────────────────
1. Go to "Email Templates" → "Create New Template"
2. Set "To Email" to: {{to_email}}
3. Set Subject to something like: New SB 350 Application — {{first_name}} {{last_name}}
4. In the Body, paste this template:

----
New Application Received

Name:             {{first_name}} {{last_name}}
Address:          {{address}}
Renovation Type:  {{renovation_type}}

── FINANCE ──
Credit Score:     {{credit_score}}
Monthly Income:   {{monthly_income}}
Home Loan:        {{home_loan}}
  Payment/mo:     {{home_loan_payment}}
Credit Card Debt: {{credit_card_debt}}
  Payment/mo:     {{cc_debt_payment}}

── DECISION ──
Status:           {{decision}}
Rebate Type:      {{rebate_type}}
Rebate Value:     {{rebate_value}}
----

5. Save the template and note down the TEMPLATE ID (looks like "template_xxxxxxx")

─────────────────────────────────────────
STEP 4 — Add your keys to index.html
─────────────────────────────────────────
Open index.html in any text editor (Notepad, VS Code, etc.)
Find this block near the bottom of the file (search for "TODO"):

  const EMAILJS_PUBLIC_KEY  = "YOUR_PUBLIC_KEY";
  const EMAILJS_SERVICE_ID  = "YOUR_SERVICE_ID";
  const EMAILJS_TEMPLATE_ID = "YOUR_TEMPLATE_ID";

Replace the placeholder values with your actual keys:
- PUBLIC KEY  → EmailJS dashboard → Account → General → Public Key
- SERVICE ID  → from Step 2
- TEMPLATE ID → from Step 3

Save the file.

─────────────────────────────────────────
STEP 5 — Open and test
─────────────────────────────────────────
1. Double-click index.html to open it in your browser
2. Fill out the form
3. In "Advanced Settings", enter your email address
4. Click "Submit Application"
5. Check your inbox — the submission should arrive within seconds

─────────────────────────────────────────
NOTES
─────────────────────────────────────────
- Photos attached to the form are NOT emailed (EmailJS free tier does not
  support attachments). The file names are listed in the submission for reference.
- Free EmailJS plan: 200 emails/month, 2 templates.
- No server, hosting, or database needed — the file works locally.
