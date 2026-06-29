# Apollo MCP Integration Guide: Contact Enrichment for Security Hiring Leads

## Overview

This guide teaches Account Executives how to use **Apollo MCP** — a contact enrichment tool integrated into Claude Code — to find and verify email addresses and phone numbers for hiring managers identified through Exa MCP searches.

### What is Apollo MCP?

Apollo MCP is a B2B contact database and email lookup tool that allows you to:
- **Search for professional contacts** by company name, title, and location
- **Verify email addresses** with high accuracy
- **Retrieve phone numbers** for direct outreach
- **Batch enrich** multiple contacts simultaneously
- **Access employment history** and profile data

Think of it as your contact directory for decision-makers — essential for converting research leads into actual conversations.

### Why We Use Apollo MCP for Hiring Manager Enrichment

1. **Find Email Addresses** – The most reliable way to contact hiring managers (beats phone prospecting)
2. **Verify Phone Numbers** – Get direct lines when emails fail or for multi-touch outreach
3. **Reduce False Leads** – Confirm the person exists and works at the company
4. **Enable Batch Processing** – Enrich 10-20 leads at once vs. manual Googling
5. **Save Time** – Replace LinkedIn stalking + email guessing with verified data
6. **Enable Personalization** – Direct contact info enables personalized discovery angles

### How It Connects to the Workflow

```
Exa Search → Airtable → Apollo Enrichment → Score & Research → Call Angle
  (Task 3)    (Task 3)      (Task 4)         (Task 5)      (Task 5)
                ↓
        Company + Manager Name
                ↓
         Apollo Enrichment
                ↓
         Email + Phone
                ↓
          Airtable Updated
                ↓
        Ready for Outreach
```

**Your role in this workflow:**
- Extract company names and hiring manager names from Exa research
- Use Apollo MCP to look up verified contact info
- Populate Airtable Email and Phone fields
- Prepare for personalized outreach

---

## Prerequisites

Before you start:

1. **Claude Code installed** with Apollo MCP available
   - If you don't have Claude Code: https://claude.com/claude-code
   - Apollo MCP is built into Claude Code's MCP ecosystem
   - No additional installation required (already available globally)

2. **Basic familiarity with Claude Code**
   - Know how to invoke MCP tools
   - Comfortable with command syntax and parameters
   - Can copy-paste data into/from Airtable

3. **Access to Airtable base** (SecurityLeads)
   - Your Airtable base created and configured (see Task 1: Airtable Setup)
   - Edit access to the SecurityLeads table
   - Familiarity with Company Name, Email, and Phone fields

4. **Data from Exa MCP research**
   - Company names from job postings
   - Job titles or positions (to identify hiring managers)
   - Optionally: hiring manager names if mentioned in posting
   - Optionally: company contact/recruiting team info

5. **Singapore context**
   - Familiar with Singapore phone number format: +65 XXXX XXXX (8 digits)
   - Know common Singapore companies and industries
   - Understand that some companies may have regional offices

---

## Core Enrichment Workflow

### Part A: Prepare Batch for Enrichment

Before calling Apollo, you need to organize your data. This stage happens in Airtable.

#### What Information You Need

For effective Apollo enrichment, have this information ready:

**Required:**
- **Company Name** – Legal company name (exact spelling matters)
  - Example: "DBS Bank Ltd" (not "DBS" or "DBS Banking")
  - Tip: Use the official company name from the job posting or website

**Optional but Helpful:**
- **Hiring Manager Name** – If mentioned in job posting
  - Example: "Sarah Chen" or "Raj Patel"
  - If not available, use job title instead
- **Job Title/Position** – To narrow down results
  - Example: "CISO", "VP of Security", "Head of Information Security"
- **Location** – Always "Singapore" for our workflow

**Nice to Have:**
- **Company website** – For verification
- **Job posting URL** – Source of the hiring signal
- **Department** – "Security", "Information Security", "Risk & Compliance"

#### Which Airtable Fields to Populate

After Apollo enrichment, populate these fields in Airtable:

| Field | Data Type | What to Capture | Example |
|-------|-----------|-----------------|---------|
| **Email** | Email | Primary email for hiring manager | john.smith@dbs.com |
| **Phone** | Text/Phone | Direct phone number with +65 country code | +65 6555 1234 |
| **Enriched** | Checkbox (optional) | Mark as completed enrichment batch | ✓ |

**Important:** Keep Company Name and Job Title fields filled out correctly before enrichment — these are your lookup keys.

#### Batch Size Recommendation

Work in batches of **10-20 rows** per enrichment session. Why?

- **10 rows:** Ideal for quick turnaround (5-10 min per batch)
- **15 rows:** Sweet spot for efficiency vs. quality checking
- **20 rows:** Maximum before you start making mistakes copying data back to Airtable

**Workflow:**
1. Identify 10-20 rows in Airtable with Company Name but missing Email/Phone
2. Copy company names + job titles into Apollo (batch query)
3. Get results back
4. Verify quality (check confidence scores)
5. Copy results into Airtable Email + Phone fields
6. Move to next batch

#### Preparation Checklist

Before you call Apollo, verify:

- [ ] Company Name is spelled exactly as it appears officially
- [ ] Job Title or hiring manager name is clearly noted
- [ ] You have 10-20 rows ready for lookup
- [ ] Airtable Email and Phone fields are empty (ready for data)
- [ ] You know which hiring manager you're looking for (title-based if name unknown)
- [ ] Singapore location is confirmed for all rows

---

### Part B: Call Apollo MCP

#### Command Syntax and Basic Usage

Apollo MCP can be called from Claude Code. The basic syntax:

```
apollo search [parameters]
```

**Core Parameters:**

| Parameter | Value | Example | Required? |
|-----------|-------|---------|-----------|
| `--company` | Company legal name | "DBS Bank Ltd" | Yes |
| `--name` | Specific person name | "Sarah Chen" | No |
| `--title` | Job title | "CISO" or "Chief Information Security Officer" | Recommended |
| `--location` | City/Region | "Singapore" | Recommended |
| `--department` | Department name | "Information Security" or "Risk" | Optional |

#### Example Queries for Different Scenarios

**Scenario 1: Known Hiring Manager Name**
```
apollo search --company "DBS Bank Ltd" --name "Sarah Chen" --location "Singapore"
```
*Use this when you found the manager's name in the job posting or LinkedIn*

**Scenario 2: Title-Based Search (Most Common)**
```
apollo search --company "DBS Bank Ltd" --title "Chief Information Security Officer" --location "Singapore"
```
*Use this when you know the position but not the person's name*

**Scenario 3: Generic Title**
```
apollo search --company "Grab" --title "Head of Security" --location "Singapore"
```
*For organizations with less common security titles*

**Scenario 4: Multiple Titles (Company Hiring Multiple Roles)**
```
apollo search --company "Singtel" --title "CISO" --location "Singapore"
apollo search --company "Singtel" --title "Security Director" --location "Singapore"
```
*Search separately for different titles within same company*

**Scenario 5: Company with Regional Office (Verify Primary)**
```
apollo search --company "Microsoft Singapore Pte Ltd" --title "Security Manager" --location "Singapore"
```
*Use the full legal entity name for accuracy*

#### How to Handle Missing Information

**Problem: You don't know the hiring manager's name**
- Solution: Use Apollo's `--title` parameter instead
- Try the most senior security title first (CISO, VP Security)
- If no results, try broader titles (Security Manager, Security Director)

**Problem: Company name spelling is uncertain**
- Solution: Try the most common variant first
- If no results, ask: "What's the company legal name?" in Airtable
- Example: "DBS" vs "DBS Bank Ltd" vs "DBS Bank (Singapore) Limited"
- Tip: Check the official job posting or company website for exact name

**Problem: Multiple people might fit the title**
- Solution: Apollo returns ranked results by likelihood (confidence score)
- Use the highest confidence match (see Interpret Results section below)
- If unsure, verify via LinkedIn profile match

**Problem: Startup or smaller company not in Apollo database**
- Solution: Use alternative lookup (LinkedIn, company email format)
- Document as "Not in Apollo DB" in Airtable notes
- Try Apollo again after 30 days (new companies added regularly)

#### Query Tips for Singapore Context

**Do's:**
- ✓ Use `--location "Singapore"` to filter regional results
- ✓ Use full legal company name from official sources
- ✓ Try CEO/Founder name if CISO unknown (they often own security in startups)
- ✓ Use job title variations if first search fails (e.g., "Head of Security" vs "VP Security")

**Don'ts:**
- ✗ Don't use company abbreviations (DBS not DBSSG)
- ✗ Don't search "Asia-Pacific" location (too broad)
- ✗ Don't assume title format (check official posting)
- ✗ Don't include "Pte Ltd" if shorter name works

#### Batch Query Example

For efficiency, here's how to batch lookup 3-5 contacts:

```
Query Set A: Financial Services
apollo search --company "DBS Bank Ltd" --title "CISO" --location "Singapore"
apollo search --company "Singtel" --title "VP of Security" --location "Singapore"
apollo search --company "CapitaLand Investment Limited" --title "Chief Risk Officer" --location "Singapore"

Query Set B: Tech/E-Commerce
apollo search --company "Grab" --title "Head of Information Security" --location "Singapore"
apollo search --company "Lazada Singapore" --title "Security Manager" --location "Singapore"
```

**Batch strategy:** Group by industry, then run all queries together for efficiency.

---

### Part C: Interpret Results

#### What Apollo Returns

When Apollo finds a match, it typically returns:

```json
{
  "name": "John Smith",
  "title": "Chief Information Security Officer",
  "company": "DBS Bank Ltd",
  "email": "john.smith@dbs.com",
  "phone": "+65 6555 1234",
  "confidence_score": 95,
  "profile_url": "https://apollo.io/profiles/...",
  "employment_history": [
    {
      "company": "DBS Bank Ltd",
      "title": "CISO",
      "start": "2022",
      "end": "present"
    }
  ]
}
```

**Key fields to understand:**

| Field | What It Means | What You Do |
|-------|---------------|------------|
| **name** | Contact's full name | Verify matches your search (e.g., if you searched "Sarah Chen", confirm match) |
| **email** | Primary email address | Copy to Airtable Email field (this is your primary outreach channel) |
| **phone** | Direct phone number | Copy to Airtable Phone field in format +65 XXXX XXXX |
| **confidence_score** | Apollo's confidence in the match (0-100) | Use this to decide accept/reject (see table below) |
| **title** | Job title at company | Verify this matches the job posting or expected position |
| **employment_history** | Previous roles | Useful for context (e.g., if they recently joined) |

#### When to Accept vs. Reject Results

**Confidence Score Interpretation:**

| Score | Decision | What It Means | Action |
|-------|----------|---------------|--------|
| 90-100 | ✓ ACCEPT | Nearly certain match | Copy to Airtable immediately |
| 80-89 | ✓ ACCEPT (with note) | High likelihood match | Copy to Airtable, add research note |
| 70-79 | ⚠ VERIFY | Likely match but not certain | Check LinkedIn before copying to Airtable |
| 50-69 | ✗ REJECT | Uncertain match | Skip or try different query |
| <50 | ✗ REJECT | Poor match | Try alternative search or mark as "No Match Found" |

**Accept Criteria (All of these should match):**
- [ ] Company name matches exactly
- [ ] Job title is in security/risk/compliance domain
- [ ] Confidence score ≥ 80
- [ ] Current employment (not outdated)
- [ ] No obvious data quality issues

**Reject Criteria (Any of these = skip):**
- [ ] Person left the company (end date in past)
- [ ] Title is not in security domain (e.g., "VP Marketing")
- [ ] Confidence score < 70
- [ ] Name doesn't match your search intent
- [ ] Wrong location or company

#### Example: Interpreting Ambiguous Results

**Scenario:** You search for "Security Manager" at "TechCorp Singapore" and get back 3 results:

**Result A:**
- Name: Alice Wong
- Title: Senior Security Manager
- Email: alice.wong@techcorp-sg.com
- Confidence: 94
- **Decision: ACCEPT** ✓ (Exact role match, high confidence)

**Result B:**
- Name: Bob Chen
- Title: Information Security Manager
- Email: bob.chen@techcorp-sg.com
- Confidence: 85
- **Decision: ACCEPT** ✓ (Variant of role, still high confidence)

**Result C:**
- Name: Carol Smith
- Title: IT Manager (Infrastructure)
- Email: carol.smith@techcorp-sg.com
- Confidence: 62
- **Decision: REJECT** ✗ (Wrong specialty, low confidence; she owns infrastructure, not security)

#### How to Handle Multiple Matches

**If Apollo returns multiple high-confidence matches:**

1. **Prioritize by title seniority:** CISO > VP > Manager > Engineer
2. **Use most recent match:** Check employment dates; prefer current role
3. **Pick the directly responsible person:** 
   - For CISO hiring: contact the CISO
   - For Manager-level hiring: contact the Manager
   - If both CISO and Manager exist: contact Manager first (more likely to engage)
4. **Pick one per company:** Don't contact multiple people at same company in first outreach

**Example:**
- Company: "DBS Bank Ltd"
- Posting: "VP of Information Security"
- Apollo returns: CISO (confidence 92) + VP Security (confidence 88)
- Decision: Contact the VP Security (directly responsible for the role), note CISO as escalation path

#### What Confidence Score Really Means

Apollo's confidence score reflects:
- **Data freshness** – Recently updated profiles score higher
- **Match completeness** – More fields match = higher score
- **Database prevalence** – Common names/titles may score lower (more false positives)
- **Verification status** – Verified emails/phone score higher

**The key rule:** 80+ confidence means "safe to outreach". Below 70 means "verify first or skip".

---

### Part D: Capture in Airtable

#### Copy Email to Email Field

**Standard format:**
- Take the email returned by Apollo as-is
- Format should be: `firstname.lastname@company.com` or `firstnamelastname@company.com`
- Example: `john.smith@dbs.com` or `jsmith@dbs.com`

**Quality checks:**
- ✓ Email contains @ symbol and company domain
- ✓ Email matches company domain (john.smith@dbs.com is for DBS)
- ✓ No special characters or spaces
- ✓ Ends with company domain, not Gmail/Hotmail (indicates personal)

**Example workflow:**
1. Apollo returns: `sarah.chen@grabapp.com`
2. Verify: Is Grab's domain grabapp.com? (Yes)
3. Copy to Airtable Email field
4. Done!

#### Copy Phone to Phone Field

**Singapore phone format:**
- Apollo may return: `+65 6555 1234` or `6555-1234` or `65551234`
- **Standardize to:** `+65 XXXX XXXX` (with country code and space)
- **Example:** `+65 6555 1234` (not `6555 1234`)

**Why the format matters:**
- International format (+65) is recognizable globally
- Space after country code is standard
- 8 digits is correct for Singapore landlines

**Quality checks:**
- ✓ Starts with +65
- ✓ Contains exactly 8 digits after country code
- ✓ Formatted as `+65 XXXX XXXX`
- ✓ Is a valid Singapore number (landline or mobile)

**Phone number examples:**
| Raw Apollo Output | Correct Format | Notes |
|------------------|------------------|-------|
| 6555 1234 | +65 6555 1234 | Add country code |
| 65 6555 1234 | +65 6555 1234 | Replace 65 with +65 |
| +65-6555-1234 | +65 6555 1234 | Replace hyphens with space |
| +65 (6555) 1234 | +65 6555 1234 | Remove parentheses |
| 62887766 | +65 6288 7766 | Mobile number, add country code |

#### Mark as Enriched (Optional Tracking)

If you created an "Enriched" checkbox field in Airtable:
- ✓ Check the box after successfully copying email + phone
- Helps you track which rows are enrichment-ready
- Useful for batch audits ("20 rows enriched this session")

#### Handle Missing Results Gracefully

**Scenario: Apollo finds no match or returns low-confidence results**

Option 1: **Try Alternative Query**
- Re-search with different job title
- Use company website to find hiring contact
- Search LinkedIn for the person name (if visible in posting)

Option 2: **Mark as "No Match Found"**
- Add note to Research Notes field: "Not in Apollo DB - try LinkedIn"
- Leave Email/Phone empty (don't guess)
- Continue to next row

Option 3: **Use Generic Contact Method**
- Leave Email blank
- Add note: "Contact via company careers page"
- Use public company phone if found

Option 4: **Try Later**
- Apollo database updates regularly
- Some new companies or people take weeks to appear
- Save for re-enrichment batch next month

**Example Airtable row with missing enrichment:**

| Company | Job Title | Email | Phone | Research Notes |
|---------|-----------|-------|-------|-----------------|
| TechStartup XYZ | VP Security | — | — | Not found in Apollo (startup too new). Contact via careers@techxyz.com |

---

## Batch Processing Strategy

### How to Batch Enrich Efficiently

**Optimal workflow:**

1. **Prepare batch (5 min)**
   - Open Airtable
   - Identify 10-20 rows with Company Name + Job Title, but missing Email/Phone
   - Copy company names + titles to text document for reference
   - Group by industry if possible

2. **Query Apollo (10-15 min)**
   - Open Claude Code with Apollo MCP
   - Run 10-15 searches (one per row)
   - Use batch query format for efficiency
   - Capture all results

3. **Verify results (5 min)**
   - Check confidence scores
   - Spot-check 1-2 results against LinkedIn
   - Flag any low-confidence matches

4. **Populate Airtable (10 min)**
   - Copy emails into Email field
   - Copy phones into Phone field (standardize format)
   - Check "Enriched" checkbox
   - Add notes for any rejections

5. **Quality check (5 min)**
   - Scan Airtable for obvious errors
   - Verify 2-3 email domains match company names
   - Confirm phone numbers are 8 digits
   - Done!

**Total time per batch:** 30-45 min for 10-15 leads

### Time Estimates Per Batch

| Batch Size | Query Time | Verification | Airtable Entry | Total Time |
|----------|-----------|--------------|---|---|
| 5 leads | 5 min | 2 min | 5 min | **12 min** |
| 10 leads | 10 min | 4 min | 8 min | **22 min** |
| 15 leads | 15 min | 5 min | 10 min | **30 min** |
| 20 leads | 20 min | 6 min | 12 min | **38 min** |

**Efficiency tip:** Batch of 15 leads in 30 min = 2 leads per minute. Best ROI on your time.

### Re-Run Strategy if First Attempt Fails

**If Apollo finds no matches on first try:**

**Attempt 2 (10 min later):**
- Check company name spelling
- Simplify title (e.g., "CISO" instead of "Chief Information Security Officer")
- Remove location filter and search globally first, then verify Singapore

**Attempt 3 (next day):**
- Try alternative job titles within security
- Search company CEO/Founder (they often own security in startups)
- Search for "Security", "Risk", or "Compliance" roles

**Attempt 4 (later):**
- Use LinkedIn or company website
- Document as "Apollo lookup failed" + manual research needed
- Don't skip enrichment — find contact another way

### When to Move On (Accept "No Match")

**Set this decision rule:**
- If 2-3 different Apollo queries return no results with confidence > 70
- AND you've tried company name variations
- AND the company is small or very new (<2 years old)
- **Then:** Mark as "Not in Apollo DB" and move on

**Why move on?** Spending 30 min looking up one contact is inefficient. Better to enrich 9/10 contacts well than chase perfect data.

---

## Edge Cases & Troubleshooting

### No Contact Found (Backup Strategies)

**Problem:** Apollo returns zero results for a company/title combination.

**Backup Strategy 1: Generic Company Email**
```
If Apollo fails for "DBS Bank Ltd" + "CISO"
→ Try company website's "Careers" or "Contact" page
→ Find email pattern (firstname.lastname@dbs.com)
→ Guess: "security@dbs.com" or "ciso@dbs.com" (lower confidence)
```

**Backup Strategy 2: LinkedIn Search**
```
Go to LinkedIn, search:
- Company: "DBS Bank"
- Title: "Chief Information Security Officer" OR "CISO"
- Location: "Singapore"
→ Find most recent hire or current CISO
→ View profile for email/phone hints
→ Leave Airtable blank if no email found
```

**Backup Strategy 3: Company Website**
```
Visit company.com/careers or company.com/contact
→ Look for "Security Leadership" or team pages
→ Find CISO/VP Security name
→ Email often firstname.lastname@company.com
```

**Backup Strategy 4: Accept Missing Data**
```
Document in Airtable:
- Email: [empty]
- Phone: [empty]
- Research Notes: "Contact via careers@company.com" or "Call main line +65 6XXX XXXX"
→ Use secondary outreach method (company email or main phone)
```

### Multiple Matches (Which to Choose)

**Problem:** Apollo returns 3-5 people with "CISO" title at the same company.

**Decision Tree:**

```
Are they at the same company?
├─ YES → Check employment dates
│  ├─ Multiple current CISOs? Rare but possible
│  │  └─ Choose the one listed as primary CISO (check titles)
│  └─ One current, others historical?
│     └─ Choose the current one (highest confidence)
│
├─ NO (different companies) → This is actually OK
│  └─ You have options; contact the most senior
```

**Example: DBS Bank CISO Search Returns:**

| Rank | Name | Title | Current? | Confidence | Action |
|------|------|-------|----------|-----------|--------|
| 1 | John Smith | Chief Information Security Officer | Yes (2022-present) | 95 | ✓ CHOOSE THIS |
| 2 | Sarah Chen | VP Information Security | Yes | 88 | Alternative/escalation |
| 3 | Bob Johnson | CISO | No (2018-2021) | 92 | Outdated; skip |

**Rule:** Always pick the person with most current employment (end date = "present"), then highest confidence.

### Invalid Company Name (Spelling Variations)

**Problem:** "Singtel" vs "Singapore Telecommunications Limited" vs "Singtel Optus" (Australia) — which is correct?

**How to resolve:**

1. **Check the job posting** – What company name did they use?
   - Example: Job posted on "Singtel Careers" or "DBS Careers"

2. **Check official company website** – Visit company.com
   - Example: `www.singtel.com` → likely "Singtel" officially

3. **Try variations in Apollo** – Query both, keep highest confidence result
   - Query 1: `--company "Singtel"`
   - Query 2: `--company "Singapore Telecommunications Limited"`
   - Use whichever returns results

4. **Document the official name** – Update Airtable Company Name field
   - Consistency helps for future re-enrichment

**Common Singapore company name variations:**

| Shorthand | Official Name | Apollo Query |
|-----------|--------------|--------------|
| DBS | DBS Bank Ltd | "DBS Bank Ltd" |
| Singtel | Singapore Telecommunications Limited | "Singtel" or "Singapore Telecommunications" |
| OCBC | Oversea-Chinese Banking Corporation | "OCBC Bank" |
| Grab | Grab Holdings Inc (Singapore) | "Grab" or "Grab Singapore" |
| Lazada | Lazada Southeast Asia | "Lazada Singapore" or "Alibaba Lazada" |

**Pro tip:** If unsure, search the shorter version first — Apollo usually handles aliases automatically.

### Missing Hiring Manager Info (Use Generic Title)

**Problem:** Job posting doesn't mention hiring manager name, only position.

**Solution: Use Job Title as Search Parameter**

Instead of:
```
apollo search --company "Grab" --name "?" --location "Singapore"
```

Use:
```
apollo search --company "Grab" --title "Chief Information Security Officer" --location "Singapore"
```

**Apollo will return the person most likely filling (or recently filled) that role.**

**If still no results, try alternatives:**
- Use broader title: "CISO" → "Head of Security" → "Security Director"
- Search by department: `--department "Information Security"`
- Search by related title: "Chief Risk Officer" (if security reports to CRO)

### Singapore Phone Number Formats

**Problem:** Apollo returns phone in different format than expected.

**Standard Singapore formats:**
- Landline: 6 followed by 7 more digits → 8 total digits
  - Example: 6555 1234
- Mobile: 8 or 9 followed by 7 more digits → 8 total digits
  - Example: 8755 1234 or 9123 4567

**International format:**
- Always use `+65 XXXX XXXX` (with +65 country code)
- Apollo may return: `+65-6555-1234` or `6555 1234`
- Standardize to: `+65 6555 1234` (replace hyphens with space, add +65 if missing)

**Validation checks:**
- ✓ After +65, exactly 8 digits
- ✓ No letters or special characters
- ✓ Starts with 6, 8, or 9 (valid Singapore prefix)

**Example conversions:**

| Input Format | Standard Format | Valid? |
|---|---|---|
| 6555 1234 | +65 6555 1234 | ✓ |
| +6565551234 | +65 6555 1234 | ✓ |
| 65 6555 1234 | +65 6555 1234 | ✓ |
| +65-6555-1234 | +65 6555 1234 | ✓ |
| 555 1234 | Invalid (only 7 digits) | ✗ |
| +65 800 1234 | +65 8001 1234 | ✓ |

---

## Integration Tips

### Timing: When to Enrich (After Exa Research, Before Call Prep)

**Optimal workflow sequence:**

```
Day 1 (Morning):
  - Search job postings with Exa MCP (Task 3)
  - Add promising leads to Airtable
  - Document company + job title

Day 1 (Afternoon):
  - Run Apollo enrichment on batch of 10-15 leads
  - Populate Email + Phone fields
  - Update Airtable

Day 2 (Morning):
  - Review Tier Scores (auto-calculated in Airtable)
  - Research top Tier 1/2 leads manually
  - Write Call Angle for highest-scoring prospects
  - Review results before calling

Day 2 (Afternoon):
  - Make discovery calls with enriched contact info
```

**Why this timing?**
- Enrichment before research saves time (have email before deep dive)
- Fresh leads (same day or next day) have higher engage rates
- Phone enrichment enables multi-touch (email + phone = higher conversion)

### Dependencies: Requires Exa Search First

**Apollo enrichment only works if you have:**
- [ ] Company name (from Exa search)
- [ ] Job title or hiring manager context (from Exa search)
- [ ] Location (Singapore)

**Cannot use Apollo alone** — you need Exa search first to find the leads.

**Workflow dependency:**

```
Exa (Find leads) → Apollo (Enrich contacts)
        ↓
    "DBS hiring CISO"
        ↓
  "Find John Smith's email"
        ↓
    Contact Info
```

If you skip Exa and try Apollo alone, you'll query randomly without context.

### Efficiency: Batch vs. Single Enrichments

**Batch enrichment (15+ leads at once):** 30 min total
- Most efficient per lead
- Better for weekly workflow
- Easier to spot patterns/errors

**Single enrichment (1 lead):** 3-5 min per lead
- Best when you need urgent context
- Use when following up on specific lead
- Less efficient if doing 10+ lookups

**Recommendation:** Batch once a week (15-20 leads), then do spot lookups as needed.

### Fallbacks: What if Apollo Fails

**Tier 1 Fallback (If Apollo returns no results with high confidence):**

1. **LinkedIn Search** (3-5 min)
   - Search company + title
   - Find profile, check email hints
   - Note: email may not be visible

2. **Company Website** (3-5 min)
   - Visit company careers page
   - Look for CISO/VP Security team page
   - May find email format or name

3. **Email Pattern Guessing** (2 min)
   - Common formats: firstname.lastname@company.com
   - Try: first.last@company.com or firstlast@company.com
   - Risk: High bounce rate, low engagement

4. **Accept Partial Data** (1 min)
   - Leave Email blank
   - Use phone number only (if found)
   - Document: "Limited contact info available"

**Tier 2 Fallback (Use alternative contact method):**
- Call company main phone line → ask for CISO's office
- Email careers@company.com → ask for CISO contact
- Use Exa to find company employee directory

---

## Example Workflows

### Example 1: Complete Match (Company + Manager Name Known)

**Scenario:**
- Job posting: "DBS Bank Ltd hiring for Chief Information Security Officer"
- Posting includes hiring manager: "Reporting to Sarah Chen"
- You want to contact Sarah Chen

**Step 1: Prepare data in Airtable**
```
Company Name: DBS Bank Ltd
Job Title: Chief Information Security Officer
Hiring Manager: Sarah Chen
Location: Singapore
```

**Step 2: Query Apollo**
```
apollo search --company "DBS Bank Ltd" --name "Sarah Chen" --location "Singapore"
```

**Step 3: Interpret results**
```
Result:
- Name: Sarah Chen
- Title: Chief Information Security Officer
- Company: DBS Bank Ltd
- Email: sarah.chen@dbs.com
- Phone: +65 6555 1234
- Confidence: 98
- Decision: ACCEPT ✓
```

**Step 4: Update Airtable**

| Company | Job Title | Hiring Manager | Email | Phone | Notes |
|---------|-----------|-----------------|-------|-------|--------|
| DBS Bank Ltd | CISO | Sarah Chen | sarah.chen@dbs.com | +65 6555 1234 | Enriched via Apollo (confidence 98) |

**Step 5: Ready for outreach**
- Email: sarah.chen@dbs.com (primary)
- Phone: +65 6555 1234 (backup)
- Call angle: "Sarah, I noticed DBS is investing in security leadership. Let's discuss your current posture before the new CISO joins..."

**Time invested:** 8 min
**Success rate:** Excellent (direct contact, high confidence)

---

### Example 2: Partial Info (Company + Title Only)

**Scenario:**
- Job posting: "Grab hiring for Head of Information Security"
- Posting does NOT include manager name
- No specific person mentioned

**Step 1: Prepare data in Airtable**
```
Company Name: Grab
Job Title: Head of Information Security
Location: Singapore
Hiring Manager: [Unknown]
```

**Step 2: Query Apollo (title-based)**
```
apollo search --company "Grab" --title "Head of Information Security" --location "Singapore"
```

**Step 3: Interpret results**

Apollo returns:
```
Result 1:
- Name: Michael Tan
- Title: Head of Information Security
- Email: michael.tan@grab.com
- Phone: +65 8234 5678
- Confidence: 91
- Decision: ACCEPT ✓

Result 2:
- Name: Lisa Wong
- Title: VP Security (Asia-Pacific)
- Email: lisa.wong@grab.com
- Phone: +65 9123 4567
- Confidence: 87
- Decision: ACCEPT (escalation path)
```

**Step 4: Update Airtable**

| Company | Job Title | Hiring Manager | Email | Phone | Notes |
|---------|-----------|-----------------|-------|-------|--------|
| Grab | Head of Information Security | Michael Tan (Apollo) | michael.tan@grab.com | +65 8234 5678 | Apollo confidence 91; Lisa Wong (VP) available as escalation |

**Step 5: Ready for outreach**
- Primary: michael.tan@grab.com (direct manager of role)
- Escalation: lisa.wong@grab.com (VP-level, if needed)
- Call angle: "Michael, your team is growing. Let's validate your current security posture before onboarding new team members..."

**Time invested:** 10 min
**Success rate:** Good (title-based search, high confidence)

---

### Example 3: No Match Found (Fallback Strategy)

**Scenario:**
- Job posting: "TechStartup XYZ is hiring for VP Security" (very small, new company)
- Apollo query returns: Zero results or very low confidence (<70)
- Company not in Apollo database (too new or small)

**Step 1: Prepare data in Airtable**
```
Company Name: TechStartup XYZ Pte Ltd
Job Title: VP Security
Location: Singapore
```

**Step 2: Query Apollo (attempt 1)**
```
apollo search --company "TechStartup XYZ" --title "VP Security" --location "Singapore"
```

**Step 3: Interpret results**
```
Result:
- Confidence: 35
- Decision: REJECT ✗ (Too low confidence)

Try alternative:
apollo search --company "TechStartup XYZ Pte Ltd" --title "Chief Risk Officer" --location "Singapore"
→ No results

Try alternative 2:
apollo search --company "Tech Startup XYZ" --title "Security" --location "Singapore"
→ No results
```

**Step 4: Implement fallback strategy**

Option A: Check job posting for hiring contact
```
Job URL: careers.techxyz.com/vp-security-2026
→ Posting says: "Apply at careers@techxyz.com"
→ Contact method: Email careers team
```

Option B: LinkedIn search
```
Search: TechStartup XYZ + VP Security
→ Find 1 result: John Lee, VP Security, just hired 3 months ago
→ Profile: john.lee (likely john.lee@techxyz.com but not confirmed)
```

Option C: Company website
```
Visit techxyz.com/about/team
→ No security team page found
→ Only CEO listed: founder@techxyz.com
```

**Step 5: Update Airtable (partial enrichment)**

| Company | Job Title | Hiring Manager | Email | Phone | Notes |
|---------|-----------|-----------------|-------|-------|--------|
| TechStartup XYZ | VP Security | — | — | — | Not in Apollo DB (startup too new). Contact via careers@techxyz.com or try John Lee (LinkedIn). Follow up in 30 days. |

**Step 6: Alternative outreach plan**
- Email: careers@techxyz.com (generic careers inbox)
- Message: "Hi TechStartup XYZ team, I see you're building out security leadership. Happy to discuss how other growing startups approach security strategy..."
- Follow-up: LinkedIn message to John Lee (VP Security) after email

**Time invested:** 15 min
**Success rate:** Lower (generic email, but acceptable for early-stage company)

---

## Success Criteria

### When Enrichment is "Good Enough" to Proceed

**Minimum success criteria:**

You can proceed to call prep if:
- [ ] Email address found (primary channel)
- [ ] Confidence score ≥ 80
- [ ] Title matches security domain (CISO, VP, Manager, etc.)
- [ ] Current employment (not outdated)
- [ ] No obvious red flags (e.g., person left company)

**Example: Ready to proceed**
```
Email: john.smith@dbs.com ✓
Confidence: 92 ✓
Title: Chief Information Security Officer ✓
Current: 2022-present ✓
→ READY TO CALL ✓
```

**Example: NOT ready**
```
Email: john.smith@oldcompany.com ✓
Confidence: 60 ✗ (Too low)
Title: Chief Information Security Officer ✓
Current: 2018-2021 ✗ (Outdated)
→ DO NOT CALL (Wrong person, wrong company)
```

### Confidence Score Thresholds

| Score | Action | Example |
|-------|--------|---------|
| 90-100 | Proceed immediately | Email john.smith@dbs.com today |
| 80-89 | Proceed with note | Email with light research context |
| 70-79 | Verify first | Check LinkedIn before emailing |
| 50-69 | Explore alternatives | Try different query or fallback method |
| <50 | Skip | Mark as "No Match" and move on |

### When to Try Alternative Lookup Methods

Try alternatives if:
- [ ] Apollo confidence < 70 after 2+ queries
- [ ] Company appears to be startup (<2 years old)
- [ ] Apollo returns "zero results" on multiple variations
- [ ] Manual company website search reveals different person

Alternative methods:
1. LinkedIn search (company + title)
2. Company website team page
3. Job posting hiring contact email
4. Company main phone → ask for CISO
5. Accept missing enrichment for now; retry in 30 days

### What Fields Are Required vs. Optional for Calling

**REQUIRED (must have at least one):**
- [ ] **Email address** (preferred; highest conversion)
- [ ] **Phone number** (backup if email bounces)

**OPTIONAL (nice to have):**
- [ ] Hiring manager name (helps personalization)
- [ ] Direct phone line (saves time vs. main phone)
- [ ] Employment history (context for conversation)

**Example: Minimum viable data for call**
```
Company: DBS Bank Ltd
Contact: sarah.chen@dbs.com
Title: CISO
→ Enough to make discovery call
```

**Example: Ideal data for call**
```
Company: DBS Bank Ltd
Contact Name: Sarah Chen
Email: sarah.chen@dbs.com
Phone: +65 6555 1234
Title: Chief Information Security Officer
Recent history: VP Security at Singapore Bank (2018-2022)
→ Ready for personalized, contextualized discovery call
```

---

## Summary: Quick Reference

### Apollo MCP Command Cheat Sheet

```bash
# Basic search (by name)
apollo search --company "Company Name" --name "John Smith" --location "Singapore"

# Search by title (most common)
apollo search --company "Company Name" --title "CISO" --location "Singapore"

# Search by department
apollo search --company "Company Name" --department "Information Security" --location "Singapore"

# Batch search (run multiple queries)
apollo search --company "DBS Bank Ltd" --title "CISO" --location "Singapore"
apollo search --company "Grab" --title "VP Security" --location "Singapore"
apollo search --company "Singtel" --title "Security Manager" --location "Singapore"
```

### Airtable Fields to Populate

- **Email:** firstname.lastname@company.com
- **Phone:** +65 XXXX XXXX
- **Enriched:** ✓ (optional checkbox)
- **Research Notes:** Apollo confidence score + any special notes

### Decision Tree

```
Apollo finds match?
├─ YES → Confidence ≥ 80?
│  ├─ YES → Copy to Airtable → READY ✓
│  └─ NO → Verify on LinkedIn → Then copy or reject
└─ NO → Try alternative title/name → Still nothing?
   └─ Use fallback (LinkedIn/website) or skip with note
```

### Time Estimates

- Single lookup: 3-5 min
- Batch of 10-15: 30 min total (~2 min per lead)
- Quality verification: +5 min

### Success Rate

- Tier 1 companies (DBS, Singtel, Grab): 90%+ match rate
- Tier 2 companies (mid-size tech, banking): 70-80% match rate
- Startups / new companies: 20-40% match rate (try again in 30 days)

---

## Appendix: Common Issues & Solutions

### Q: Apollo says "Company not found"
**A:** Company may be too new or private. Try:
1. Full legal name (e.g., "DBS Bank Ltd" not "DBS")
2. Alternative names (e.g., "Singtel" vs "Singapore Telecommunications Limited")
3. Search again in 30 days (database updates weekly)

### Q: Apollo returns 5 people for the same title
**A:** Choose the person with:
1. Most current employment (end date = "present")
2. Highest confidence score
3. Exact title match over variations

### Q: Email bounces when I send
**A:** Apollo is usually accurate, but:
1. Verify person's LinkedIn (employment still current?)
2. Try phone number instead
3. Use company careers email as fallback

### Q: Phone number seems wrong
**A:** Verify:
1. Country code is +65 (Singapore)
2. Total of 8 digits after country code
3. Number starts with 6, 8, or 9
4. If unsure, call company main line and ask for person

### Q: How often does Apollo database update?
**A:** Apollo updates:
- Employee data: Weekly
- Company info: Monthly
- Job postings: Daily
- If no match today, try again in 7-30 days

---

## Next Steps

1. **Load Apollo MCP** in Claude Code (already available)
2. **Prepare batch** of 10-15 leads from Exa research
3. **Run enrichment** using commands in this guide
4. **Verify results** against confidence scores
5. **Populate Airtable** with email + phone
6. **Proceed to research phase** (Task 5)

Good luck with your enrichment! Email is your primary outreach channel — make it count.
