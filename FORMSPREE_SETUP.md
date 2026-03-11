# AGC — Formspree Setup Guide
## Takes 10 minutes. Completely free.

---

## What This Does

When someone fills in the **Join AGC** form or **Submit Event** form on your site,
their data gets sent directly to your email inbox — and stored in Formspree's dashboard.

---

## Step 1 — Create Your Formspree Account

1. Go to **https://formspree.io**
2. Click **Get Started Free**
3. Sign up with your email (the one you want submissions sent to)
4. Verify your email

Free plan gives you **50 submissions/month** — plenty to start.

---

## Step 2 — Create Form 1: Member Registration

1. In Formspree dashboard, click **+ New Form**
2. Name it: `AGC Member Registration`
3. Copy the **Form ID** — looks like: `xpzgkqrn` (8 characters)
4. Open `register.html` in a text editor
5. Find this line (near the bottom, inside `<script>`):
   ```
   const FORMSPREE_ID = 'YOUR_FORM_ID';
   ```
6. Replace `YOUR_FORM_ID` with your actual ID:
   ```
   const FORMSPREE_ID = 'xpzgkqrn';
   ```
7. Save the file

---

## Step 3 — Create Form 2: Event Submission

1. In Formspree dashboard, click **+ New Form** again
2. Name it: `AGC Event Submission`
3. Copy the **Form ID** (different from the first one)
4. Open `submit-event.html` in a text editor
5. Find this line:
   ```
   const FORMSPREE_ID = 'YOUR_EVENT_FORM_ID';
   ```
6. Replace with your actual ID
7. Save the file

---

## Step 4 — Push to GitHub / Vercel

After editing both files, push to GitHub.
Vercel will auto-deploy in ~30 seconds.

---

## Step 5 — Test It

1. Go to your live site: **agc-website.vercel.app/register.html**
2. Fill in a test registration (use your own name + email)
3. Submit
4. Check your inbox — you should get an email from Formspree within seconds
5. Also check your Formspree dashboard — the submission appears there too

---

## What You'll Receive Per Submission

Each member registration email will contain:

```
Subject: New AGC Member: Rahul Kamble from Germany

01_Name:         Rahul Kamble
02_Email:        rahul@email.com
03_Phone:        +91 98765 43210
04_Country:      Germany
05_City:         Berlin
06_Role:         Working Professional
07_Profession:   Software Engineer
08_Education:    Postgraduate
09_Experience:   5-10 years
10_Skills:       Python, Data Analysis, Cloud Computing
11_Interests:    Career, Tech, Entrepreneurship
12_Offers_Help:  Job Referrals | Tech Mentoring
13_Needs_Help:   Startup Advice | Legal Guidance
14_LinkedIn:     linkedin.com/in/rahul
...
```

Each event submission will contain:

```
Subject: New AGC Event: Career Meetup — Berlin, Germany

01_Event_Title:  Career Meetup for AGC Members
02_Type:         Workshop
03_Format:       In-Person
04_Date:         2025-06-15
...
14_Host_Name:    Rahul Kamble
16_Host_Email:   rahul@email.com
...
```

---

## Formspree Dashboard

At **https://formspree.io/forms** you can:
- See all submissions in a table
- Export as CSV (for tracking members in a spreadsheet)
- Set up email notifications
- Block spam submissions

---

## When You Hit 50/month Limit

Formspree paid plan is **$10/month** and gives 1000 submissions.
Or switch to Supabase (free, unlimited, real database) — Claude can set that up when ready.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Form submits but no email | Check your Formspree email is verified |
| "Submission failed" error | Double-check the Form ID is correct (8 chars, no spaces) |
| Still showing YOUR_FORM_ID | You didn't save the file after editing |
| Deployed but not working | Push the updated files to GitHub, wait 30s for Vercel |
