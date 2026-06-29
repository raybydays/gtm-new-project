# Airtable Setup Guide: GTM Security Hiring Research Workflow

## Overview

This guide walks you through creating an Airtable base to manage security hiring research. We'll create a **SecurityLeads** table with 14 carefully designed fields to track job postings, hiring signals, research progress, and call status.

**Why Airtable?**
- Centralized database for tracking all security hiring opportunities
- Flexible field types (text, dates, formulas, selections) for structured data
- Easy data entry and filtering by hand
- Foundation for future automation and integrations
- Free tier covers our workflow needs

**What you'll build:**
A single Airtable base with one table (SecurityLeads) containing 14 fields organized by function:
- **Company Information**: Company Name, Job Title, Company Size
- **Contact Details**: Hiring Manager, Email, Phone
- **Job Details**: Job URL, Posting Date
- **Research & Scoring**: Why Hiring Signal, Tier Score, Research Notes
- **Sales Process**: Call Status, Call Angle, Next Action

---

## Prerequisites

Before starting:
- Create a **free Airtable account** at [airtable.com](https://airtable.com)
- You'll need your email address and a password
- No credit card required for the free tier
- Have this guide open while working in Airtable

---

## Step-by-Step Setup

### Part 1: Create Your Airtable Base

1. **Log in to Airtable**
   - Go to [airtable.com](https://airtable.com) and sign in with your account
   - You'll see your workspace dashboard

2. **Create a New Base**
   - Click the **"+ Create"** button in the top-left
   - Choose **"Start from scratch"**
   - Name your base: `GTM Security Hiring Research`
   - Click **Create base**

3. **You'll now see the base editor**
   - Airtable will create a default table called "Table 1"
   - We'll rename and customize this table next

---

### Part 2: Rename the Table and Add Fields

1. **Rename the Default Table**
   - Right-click on "Table 1" at the top-left
   - Select **Rename table**
   - Enter: `SecurityLeads`
   - Press Enter

2. **Update the Primary Field**
   - The first column is typically "Name" (the primary field)
   - Click on the "Name" column header
   - Select **Edit field**
   - Change the field name to: `Company Name`
   - Keep the field type as **Single line text**
   - Click **Save**

3. **You now have the foundation**
   - Your table has one field: Company Name
   - We'll add the remaining 13 fields one by one

---

### Part 3: Add Each Field

Follow these steps for each field below. For each field:

1. Click the **"+"** button at the end of the column headers
2. Enter the field name
3. Select the field type from the dropdown
4. Configure any additional options (explained per field)
5. Click **Save**

#### Field 1: Company Name ✓ (Already Created)
- **Field Name:** Company Name
- **Field Type:** Single line text
- **Purpose:** Company hiring for the role
- **Notes:** This is your primary field (already set up)

---

#### Field 2: Job Title
- **Field Name:** Job Title
- **Field Type:** Single select
- **Purpose:** Categorize the security role type
- **Options to create:** (Add each as a separate option)
  - Security Engineer
  - Security Architect
  - CISO
  - VP of Security
  - Director of Security
  - Security Manager
  - Security Analyst
  - Incident Response Manager
  - Compliance Manager
  - Security Operations Manager
  - AppSec Engineer
  - Cloud Security Engineer
  - Infrastructure Security
  - Security Consultant
  - Head of Security
  - Security Operations Center (SOC) Lead
  - Threat Intelligence Analyst
  - Security Engineer - Platform

**How to add options:**
- After selecting "Single select" type, you'll see an empty options list
- Click **Add an option**
- Type the first option (e.g., "Security Engineer")
- Click **Add an option** again and repeat for all 18 options
- Click **Save** when done

---

#### Field 3: Posting Date
- **Field Name:** Posting Date
- **Field Type:** Date
- **Purpose:** When was the job posted (helps with urgency)
- **Date format:** Use default (MM/DD/YYYY)
- **Notes:** Optional field; leave blank if unknown

---

#### Field 4: Job URL
- **Field Name:** Job URL
- **Field Type:** URL
- **Purpose:** Link to the actual job posting
- **Notes:** Paste the full URL (starting with https://)

---

#### Field 5: Hiring Manager
- **Field Name:** Hiring Manager
- **Field Type:** Single line text
- **Purpose:** Name of the person managing the hire
- **Notes:** Optional; leave blank if unknown

---

#### Field 6: Email
- **Field Name:** Email
- **Field Type:** Email
- **Purpose:** Contact email for the hiring manager or recruiter
- **Notes:** Use this for outreach; leave blank if not yet acquired

---

#### Field 7: Phone
- **Field Name:** Phone
- **Field Type:** Phone Number
- **Purpose:** Phone number for direct contact
- **Notes:** Airtable will format automatically; optional field

---

#### Field 8: Company Size
- **Field Name:** Company Size
- **Field Type:** Number
- **Purpose:** Number of employees (helps assess company maturity)
- **Precision:** 0 decimal places (whole numbers only)
- **Notes:** Optional; approximate is fine

---

#### Field 9: Tier Score
- **Field Name:** Tier Score
- **Field Type:** Formula
- **Purpose:** Automatically calculated score (1-10) based on company attributes
- **Formula Placeholder:** `1` (Task 2 will replace this with the actual scoring logic)
- **Notes:** This is a placeholder for now—we'll update it in Task 2

**How to add the formula:**
- After selecting "Formula" type, you'll see a formula editor
- Enter: `1`
- Click **Save**
- We'll update this formula after creating additional fields in Task 2

---

#### Field 10: Why Hiring Signal
- **Field Name:** Why Hiring Signal
- **Field Type:** Single select
- **Purpose:** Classify the reason they're hiring
- **Options to create:**
  - Compliance (e.g., new regulation requirement)
  - Breach Recovery (post-incident hiring)
  - Growth (business expansion)
  - Unknown (reason not yet determined)

---

#### Field 11: Research Notes
- **Field Name:** Research Notes
- **Field Type:** Long text
- **Purpose:** Store detailed research findings about the company and role
- **Notes:** Use this to document company background, team structure, tech stack, etc.

---

#### Field 12: Call Status
- **Field Name:** Call Status
- **Field Type:** Single select
- **Purpose:** Track where the lead is in the sales pipeline
- **Options to create:**
  - Prospect (not yet contacted)
  - Researched (company researched, not contacted)
  - Called (reached out; awaiting response)
  - Qualified (confirmed interest; next meeting scheduled)
  - Won (customer acquired)
  - Lost (not interested or bad fit)

---

#### Field 13: Call Angle
- **Field Name:** Call Angle
- **Field Type:** Long text
- **Purpose:** Store your personalized pitch/angle for this prospect
- **Notes:** Why should THEY care? What problem do you solve for them specifically?

---

#### Field 14: Next Action
- **Field Name:** Next Action
- **Field Type:** Single line text
- **Purpose:** One-line note on what to do next
- **Examples:**
  - "Follow up via email Friday"
  - "Schedule demo"
  - "Wait for reply"
  - "Research team structure"

---

## Field Configuration Summary Table

Below is a quick reference of all 14 fields and their types:

| # | Field Name | Type | Required? | Notes |
|---|---|---|---|---|
| 1 | Company Name | Single line text | Yes | Primary field |
| 2 | Job Title | Single select (18 options) | Yes | Categorize role type |
| 3 | Posting Date | Date | No | When job was posted |
| 4 | Job URL | URL | No | Link to posting |
| 5 | Hiring Manager | Single line text | No | Contact name |
| 6 | Email | Email | No | For outreach |
| 7 | Phone | Phone Number | No | Direct contact |
| 8 | Company Size | Number | No | Employee count |
| 9 | Tier Score | Formula | Yes | Placeholder: `1` (update in Task 2) |
| 10 | Why Hiring Signal | Single select (4 options) | Yes | Hiring reason |
| 11 | Research Notes | Long text | No | Detailed findings |
| 12 | Call Status | Single select (6 options) | Yes | Pipeline stage |
| 13 | Call Angle | Long text | No | Personalized pitch |
| 14 | Next Action | Single line text | No | Action reminder |

---

## Tips for Data Entry

1. **Start with the essentials:**
   - Always fill in: Company Name, Job Title, Why Hiring Signal, Call Status
   - These fields help you organize and filter your research

2. **Update as you learn:**
   - Add email/phone when you find contacts
   - Add research notes as you investigate
   - Update Call Status as you progress through the sales pipeline

3. **Use filters and sorting:**
   - Click the filter icon in Airtable to show only certain job titles
   - Sort by Posting Date (newest first) to find fresh leads
   - Filter by Call Status to see what needs action

4. **Batch data entry:**
   - Consider collecting multiple leads before entering them all at once
   - Use keyboard shortcuts: Tab to move to the next field, Enter to move to the next row

5. **Keep URLs clean:**
   - When pasting Job URLs, use the full URL (https://example.com/jobs/...)
   - Airtable will create clickable links automatically

---

## What's Next?

You've successfully created the **SecurityLeads** table with all 14 fields. 

**Next steps (Task 2):**
1. We'll create the actual **Tier Score formula** that evaluates company size, growth, and other factors
2. We'll add additional fields to support scoring (if needed)
3. We'll test the formula with sample data

**In the meantime:**
- Start adding your first few security job postings to the table
- Fill in as much detail as you can for each lead
- Get comfortable with the Airtable UI

---

## Troubleshooting

**Q: Can I change a field type after creating it?**
- Yes! Click the field header, select "Edit field," and choose a new type. Note: Changing types may cause data loss if incompatible.

**Q: Do I need to fill all fields for every record?**
- No. Only Company Name, Job Title, Why Hiring Signal, and Call Status are essential. Fill other fields as you gather information.

**Q: Can I add more fields later?**
- Absolutely. Click the **"+"** at the end of the columns anytime to add new fields.

**Q: How do I delete a record?**
- Click the record number on the left, then select "Delete record" from the menu.

**Q: How do I share this base with a team?**
- Click the **Share** button in the top-right, then add team members' email addresses. Airtable will handle permissions.

---

## Reference: Job Title Options

When creating the **Job Title** field's Single select options, here are all 18 options to add:

1. Security Engineer
2. Security Architect
3. CISO
4. VP of Security
5. Director of Security
6. Security Manager
7. Security Analyst
8. Incident Response Manager
9. Compliance Manager
10. Security Operations Manager
11. AppSec Engineer
12. Cloud Security Engineer
13. Infrastructure Security
14. Security Consultant
15. Head of Security
16. Security Operations Center (SOC) Lead
17. Threat Intelligence Analyst
18. Security Engineer - Platform

---

## Setup Verification Checklist

After completing the setup, verify you have:

- [ ] Created an Airtable base named "GTM Security Hiring Research"
- [ ] Created a table named "SecurityLeads"
- [ ] Added all 14 fields with correct types
- [ ] Verified Job Title has all 18 options
- [ ] Verified Why Hiring Signal has 4 options (Compliance, Breach Recovery, Growth, Unknown)
- [ ] Verified Call Status has 6 options (Prospect, Researched, Called, Qualified, Won, Lost)
- [ ] Added at least one test record to verify the table works
- [ ] Confirmed Tier Score formula field shows a value (currently placeholder "1")
- [ ] Tested that you can filter by Job Title, Why Hiring Signal, and Call Status

**Once you've verified all items**, you're ready for Task 2: Create the Tier Score formula.

---

## Additional Resources

- **Airtable Help Center:** https://support.airtable.com/
- **Field Type Guide:** https://support.airtable.com/hc/en-us/articles/203255215
- **Formula Reference:** https://support.airtable.com/hc/en-us/articles/203255215 (includes formula functions)

---

**Setup completed:** You now have a fully configured Airtable base ready for security hiring research.

Next task: Implement the Tier Score formula to automatically evaluate lead quality.
