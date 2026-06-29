# Exa MCP (XRCP) Integration Guide: Security Job Research for Singapore

## Overview

This guide teaches Account Executives how to use **Exa MCP (XRCP)** — a powerful web search and scraping tool integrated into Claude Code — to find security job postings in Singapore and research the companies hiring them.

### What is Exa MCP?

Exa MCP is a real-time web search and content scraping tool that allows you to:
- **Search the web** for specific job postings, company announcements, and news
- **Extract job details** (title, company, posting date, job description)
- **Scrape company information** from websites (team size, funding, recent news, products)
- **Perform targeted research** to understand why companies are hiring

Think of it as a precision web scraper — much more powerful than Google for structured research tasks.

### Why We Use Exa MCP for Security Hiring Research

1. **Find Tier-1 Opportunities** – Locate CISO and VP Security positions (rarest, highest value)
2. **Verify Job Postings** – Get direct URLs and posting dates from source
3. **Understand Hiring Context** – Research WHY companies are hiring (compliance, growth, breach recovery)
4. **Competitive Intel** – Find companies expanding security teams (growth signals)
5. **Speed Up Research** – Replace manual Googling with structured, repeatable queries

### How It Connects to the Workflow

```
Exa Search → Job Posting Found → Add to Airtable → Apollo Enrichment → Score & Research → Call Angle
   (Task 3)       (Task 3)          (Task 3)         (Task 4)      (Task 5)      (Task 5)
```

**Your role in this workflow:**
- Use Exa MCP to search for job postings
- Identify high-value leads (Tier Score framework)
- Research company context (growth, compliance, breach signals)
- Feed data into Airtable for enrichment and scoring

---

## Prerequisites

Before you start:

1. **Claude Code installed** with Exa MCP available
   - If you don't have Claude Code: https://claude.com/claude-code
   - Exa MCP is built into Claude Code's tool ecosystem

2. **Basic familiarity with Claude Code**
   - Know how to open the chat interface
   - Understand how to invoke tools/MCP servers
   - Can copy-paste URLs and data

3. **Access to Airtable base** (SecurityLeads)
   - Your Airtable base should be created (see Task 1: Airtable Setup)
   - You have edit access to the SecurityLeads table
   - Know your base URL for pasting job postings

4. **Understanding of Tier Score framework**
   - Familiar with job title tiers (CISO=Tier 1, Manager=Tier 2, etc.)
   - Know what "Why Hiring Signal" means (Compliance/Breach/Growth/Unknown)
   - See `docs/scoring-formula.md` for details

5. **Singapore context**
   - Familiar with Singapore as a tech hub
   - Know company names, industries, and size indicators
   - Comfortable with Singapore-specific job boards and sites

---

## Core Workflow: Step by Step

### Part A: Search for Job Openings

#### Query Templates & Examples

Use these query patterns in Claude Code to search for security job openings in Singapore. You can type these directly or use the Exa tool interface.

**Template 1: General Security Role Search (Broad Net)**
```
security job openings Singapore 2026 CISO "VP of Security" "Chief Information Security Officer"
```

**Template 2: Tier-1 Executive Search (Narrow, High-Value)**
```
CISO Singapore hiring job posting site:linkedin.com OR site:glassdoor.com OR site:indeed.com
```

**Template 3: Manager-Level Search (Tier 2)**
```
"Security Manager" OR "Security Operations Manager" Singapore job posting 2026
```

**Template 4: Specific Company Search (Company Context)**
```
site:company.com security hiring Singapore OR security team expansion
```

**Template 5: Growth Signal Search (Why Hiring?)**
```
Singapore company "Series A" OR "Series B" security hire team expansion
```

**Template 6: Compliance Signal Search**
```
Singapore security regulation PDPA OR compliance hiring 2026
```

#### Specific Security Role Titles to Search For

Prioritize these titles (in order):

**🔥 Tier 1 (Highest Priority):**
- CISO (Chief Information Security Officer)
- VP of Security / Chief Security Officer
- VP Information Security / Head of Security

**⭐ Tier 2 (High Priority):**
- Security Director
- Information Security Manager
- Security Operations Manager / SOC Manager

**💼 Tier 3 (Good Priority):**
- Security Architect
- Senior Security Engineer
- Compliance Manager

**📋 Tier 4 (Lower Priority, but useful for signals):**
- Security Engineer
- SOC Analyst
- Security Analyst

#### How to Filter by Location (Singapore)

When using Exa, specify Singapore in your query to avoid irrelevant results:

**Good queries:**
- `CISO Singapore job posting`
- `security hiring "Singapore, Singapore" OR "SG"`
- `site:sg/jobs security manager` (Singapore domain)

**What NOT to do:**
- Don't search just "security jobs" (returns global results)
- Avoid ambiguous terms like "CISO Asia-Pacific" (too broad)
- Skip results from regional hubs if you want Singapore specifically

#### How to Identify Tier-1 Prospects in Results

When Exa returns results, quickly scan for:

**Green flags (high-value):**
- [ ] Job title includes: CISO, VP, Chief, Head (executive level)
- [ ] Company size: 100+ employees (has budget for security)
- [ ] Posted: Within last 7 days (fresh, urgent)
- [ ] Known company: Enterprise, FinTech, Government (high risk, big budgets)
- [ ] Multiple roles: "Now hiring 3 security engineers" (scaling signal)

**Red flags (lower priority):**
- [ ] Title is generic: "Security Engineer #4" (individual contributor, no budget authority)
- [ ] Unknown company: Startup or no website (may not have budget)
- [ ] Posted: 30+ days ago (position may be filled)
- [ ] Very small company: <50 employees (limited security investment)

---

### Part B: Review & Filter Results

#### What Data Exa Returns

Exa typically returns:

```
Title:        CISO - Singapore Banking Group
Company:      XYZ Bank (Singapore) Limited
URL:          https://careers.xyzbank.com/ciso-singapore
Posted:       2026-06-22 (4 days ago)
Snippet:      "XYZ Bank is seeking an experienced CISO to lead our information security strategy..."
Company Info: Founded 2015, ~1,200 employees, Singapore headquarters
```

**Key fields to capture:**

| Field | What to Look For | Example |
|-------|------------------|---------|
| **Title** | Exact job title as listed | "CISO" or "Chief Information Security Officer" |
| **Company** | Full legal company name | "XYZ Bank (Singapore) Limited" |
| **URL** | Complete job posting URL | `https://careers.xyzbank.com/jobs/ciso-2026` |
| **Posted Date** | When job was posted | 2026-06-22 (not company founding date!) |
| **Snippet** | Job description preview | "We are seeking an experienced CISO to lead..." |
| **Company Size** | Employee count if visible | ~1,200 employees |

#### How to Identify High-Value Leads

Use this simple scoring framework while reviewing Exa results:

**Quick Lead Quality Check:**

1. **Title Score** (most important)
   - CISO/VP/Head = 90 points → **STOP. Contact immediately.**
   - Manager/Director = 75 points → **Worth researching.**
   - Architect/Engineer = 40-60 points → **Lower priority.**

2. **Recency Score**
   - Posted 0-7 days ago = +10 points (hot signal)
   - Posted 8-30 days ago = +0 points (aged)
   - Posted 30+ days ago = -10 points (skip)

3. **Company Score**
   - 500+ employees = +5 points (bigger budget)
   - 100-500 employees = +2 points (medium)
   - <100 employees = +0 points (minimal budget)

**Example scoring:**
- CISO at 800-person company, posted 3 days ago = 90 + 10 + 5 = **105 → Tier 1 Lead (Hot)**
- Security Manager at 200-person startup, posted 20 days ago = 75 + 0 + 0 = **75 → Tier 2 Lead (Good)**
- Security Engineer at 50-person company, posted 2 months ago = 40 + 0 + 0 = **40 → Tier 4 Lead (Skip)**

---

### Part C: Research Company Context (The Why)

Finding a job posting is step 1. Understanding **WHY** the company is hiring is step 2 — and equally important.

Companies hire security talent for predictable reasons. Use Exa to search for these signals:

#### Search 1: Growth Signals

**Query:**
```
[Company Name] funding Series A OR Series B OR raised OR expansion Singapore
```

**What you're looking for:**
- Recent funding announcements (signals budget + growth)
- Office expansion (new markets = new security needs)
- Headcount growth announcements
- New product launches (new systems = new security risks)

**Examples:**
- "XYZ Bank raised $50M Series B" → Growing, likely building new systems
- "TechCorp Singapore opens new office" → Expanding infrastructure, needs more security

**Why it matters:** Growth signals indicate they're investing in infrastructure and security as part of that growth. This is a good time to engage about security posture.

#### Search 2: Compliance Signals

**Query:**
```
[Company Name] PDPA OR compliance OR regulation OR certification Singapore
```

**What you're looking for:**
- New regulatory requirements (PDPA, ISO 27001, SOC 2)
- Compliance certifications announced
- Legal/regulatory news
- Data privacy statements

**Examples:**
- "XYZ Bank achieves ISO 27001 certification" → Already investing, may need more
- "Singapore introduces new data protection rules" → PDPA affects all companies

**Why it matters:** Compliance-driven hiring signals immediate need and executive prioritization. Companies that care about compliance typically have pen testing budgets.

#### Search 3: Breach or Incident Signals

**Query:**
```
[Company Name] breach OR incident OR hack OR security alert OR cybersecurity 2025 2026
```

**What you're looking for:**
- News of security incidents (major signal!)
- Breach announcements or disclosures
- Security updates/responses
- Vulnerability fixes
- Incident response team formation

**Examples:**
- "XYZ Bank discloses data breach affecting 10K users" → Hiring to recover + prevent
- "TechCorp investigating security incident" → Rebuilding security function

**Why it matters:** Post-breach hiring is a HIGH-VALUE signal. Companies are actively addressing vulnerabilities and have executive mandate (and budget) to fix security posture.

#### Search 4: Team & Leadership Signals

**Query:**
```
[Company Name] "Chief Information Security Officer" OR "Head of Security" OR CISO 2025 2026
```

**What you're looking for:**
- CISOs joining the company (executive hiring = serious)
- Leadership changes in security
- New security team announcements
- Restructuring of security function

**Examples:**
- "XYZ Bank appoints new CISO from Bank of Singapore" → Leadership is serious
- "TechCorp hires VP Security from Google" → Hiring at high level

**Why it matters:** When executives hire other executives, it signals investment and urgency. This is when they're most open to external security assessments.

#### Search 5: News & Press Releases

**Query:**
```
site:[company].com.sg security OR cybersecurity OR incident response 2026
```

**What you're looking for:**
- Company press releases about security
- Blog posts about security initiatives
- Customer trust/security messaging
- Awards or recognition (SOC 2, ISO, etc.)

**Examples:**
- "XYZ Bank launches new security center of excellence" → Active investment
- "TechCorp commits $2M to security infrastructure" → Budget confirmed

**Why it matters:** Company-published content shows their security priorities and messaging. This informs your call angle.

---

### Part D: Extract & Capture Data

Once you've found a promising lead and researched the company, it's time to capture structured data for Airtable.

#### What to Record from Job Posting

When you find a job posting, extract these fields **exactly as shown**:

| Field | Source | Example | Notes |
|-------|--------|---------|-------|
| **Company Name** | Job posting, company website | "XYZ Bank (Singapore) Limited" | Use FULL legal name, not abbreviation |
| **Job Title** | Job posting heading | "Chief Information Security Officer" | Exact title from posting, not your interpretation |
| **Job URL** | Exa result or job posting | `https://careers.xyzbank.com/ciso-2026` | Full URL starting with https:// — will paste into Airtable |
| **Posting Date** | Job posting metadata | 2026-06-22 | Month-Day-Year format; use posting date, not discovered date |
| **Hiring Manager** | Job posting, LinkedIn, company site | "John Smith" or "Hiring Team" | Name if listed; use generic if not |

#### What to Record from Company Research

When you research the company, add to Research Notes and Why Hiring Signal:

| Field | Source | Example | Notes |
|-------|--------|---------|-------|
| **Why Hiring Signal** | Exa research results | "Growth" (or "Compliance" / "Breach Recovery" / "Unknown") | Choose ONE primary signal from your research |
| **Company Size** | Company website, LinkedIn, Crunchbase | "1,200" | Employee count; approximate is OK |
| **Research Notes** | Your investigation | "Series B funded, expanding team. VP Security hire signals serious security mandate." | 2-3 sentences summarizing what you learned |

#### How Data Maps to Airtable Fields

After capturing data, you'll enter it into your Airtable SecurityLeads table:

```
Exa Search Result → Airtable Field Mapping

Job Title (from posting)      → Job Title (Single Select)
Company Name (from posting)   → Company Name (Text)
Job URL (from posting)        → Job URL (URL)
Posting Date (from posting)   → Posting Date (Date)
Hiring Manager (if found)     → Hiring Manager (Text)

Company research findings     → Research Notes (Long Text)
Growth/Compliance/Breach      → Why Hiring Signal (Single Select)
Employee count (if found)     → Company Size (Number)
```

**Example Airtable Row:**

| Field | Value |
|-------|-------|
| Company Name | XYZ Bank (Singapore) Limited |
| Job Title | Chief Information Security Officer |
| Posting Date | 2026-06-22 |
| Job URL | https://careers.xyzbank.com/jobs/ciso-2026 |
| Hiring Manager | (Not provided) |
| Company Size | 1200 |
| Why Hiring Signal | Growth |
| Research Notes | Banking sector, expanding tech team. Series B funding 2026. Hiring for new regional operations. |
| Call Status | Prospect |
| Tier Score | (Auto-calculated: 90 + 10 + 5 = 105) |

---

## Tips for Efficiency

### Batch Searching Strategies

Instead of researching one company at a time, batch your searches:

**Recommended workflow:**

1. **Phase 1: Broad Search (15 min)**
   - Run 3-4 broad queries to find all Tier 1 & 2 openings in Singapore
   - Example: `CISO Singapore 2026`, `"VP Security" Singapore site:linkedin.com`
   - Collect URLs and company names in a temporary list

2. **Phase 2: Filter Results (10 min)**
   - Review all results
   - Keep only Tier 1 (CISO/VP) and recent Tier 2 (posted <7 days)
   - Discard older postings (>30 days)

3. **Phase 3: Research Batch (20 min)**
   - For each company, run 2-3 context searches (growth, compliance, team)
   - Capture findings in your notes
   - Identify why they're hiring

4. **Phase 4: Add to Airtable (10 min)**
   - Enter all records at once
   - Copy URLs exactly
   - Fill in Why Hiring Signal based on research

**Total time: ~60 minutes for 5-10 leads.**

### Time Management Estimates

| Task | Effort | Time | Notes |
|------|--------|------|-------|
| Broad Exa search (1 query) | Low | 2-3 min | Copy-paste results |
| Review 10 results for relevance | Low | 3-5 min | Scan titles and dates |
| Deep dive: 1 company context | Medium | 5-8 min | 3 searches: growth, compliance, team |
| Add 1 lead to Airtable | Low | 2-3 min | Copy-paste fields |
| Research & write call angle | High | 10-15 min | Personalization matters |

**Per-company research: 5-10 minutes (excluding call angle writing)**

### Casting Wide vs. Narrow Nets

**Narrow Net (High Precision, Fewer Leads):**
- Focus on Tier 1 only: `CISO Singapore 2026`
- Time: 20-30 min, 2-5 leads
- Quality: High (all executive-level)
- Use when: You want to spend time on deep research per lead

**Wide Net (High Recall, More Leads):**
- Include Tier 2 & 3: `security manager Singapore 2026`
- Time: 30-45 min, 10-20 leads
- Quality: Medium (mixed seniority)
- Use when: You want a pipeline, willing to filter later

**Balanced Approach (Recommended):**
- Start with Tier 1 only
- If results are sparse (<5 leads), expand to Tier 2
- Set a time limit: "30 minutes of searching, then research"

### When to Move On from a Prospect

**Stop researching and flag "skip" if:**

- ❌ Job title is generic/junior (Security Engineer #7 at startup)
- ❌ Posted 60+ days ago (likely filled)
- ❌ Company size <50 employees (no security budget)
- ❌ Unknown company with no web presence (not established)
- ❌ Exa can't find any company information (red flag)

**Example:** Skip a Security Analyst role at a 30-person startup posted 90 days ago. It's a Tier 4 lead with no budget signals. Move to next prospect.

---

## Example Workflow: End-to-End

Let's walk through one complete example: discovering a Tier-1 opportunity and prepping it for outreach.

### Scenario
You're researching Singapore banking sector security hires. Goal: Find CISO or VP Security roles.

### Step 1: Search with Exa

**Query used:**
```
CISO Singapore banking 2026 job posting
```

**Result from Exa:**
```
Title:        Chief Information Security Officer
Company:      Singapore Digital Bank Pte Ltd
URL:          https://www.sgdigitalbank.com/careers/ciso
Posted:       2026-06-15 (14 days ago)
Snippet:      "We are looking for a visionary Chief Information Security 
              Officer to lead our security strategy as we scale our digital 
              platform. You will oversee incident response, compliance, and 
              security operations."
```

### Step 2: Extract Key Data

- Company: Singapore Digital Bank Pte Ltd
- Title: Chief Information Security Officer
- URL: https://www.sgdigitalbank.com/careers/ciso
- Posted: 2026-06-15

### Step 3: Research Company Context

**Search 1: Growth signals**
```
"Singapore Digital Bank" Series A OR Series B OR funding 2025 2026
```

**Finding:** "Singapore Digital Bank closes $30M Series B in May 2026, expanding tech team."

**Search 2: Compliance signals**
```
"Singapore Digital Bank" compliance OR PDPA OR security certification
```

**Finding:** "Company announces commitment to ISO 27001 certification by Q3 2026."

**Search 3: Team/Leadership signals**
```
site:sgdigitalbank.com security team OR CISO
```

**Finding:** "Blog post: 'Building our Security Center of Excellence — A roadmap for 2026.'"

**Assessment:** This is a HIGH-VALUE lead.
- Growing company (Series B, expanding)
- Proactive compliance investment (ISO 27001 goal)
- Leadership is serious (CCoE blog post, CISO hire)
- **Why Hiring Signal: Growth** (Series B funding + expansion)

### Step 4: Add to Airtable

**New row in SecurityLeads table:**

| Field | Value |
|-------|-------|
| Company Name | Singapore Digital Bank Pte Ltd |
| Job Title | Chief Information Security Officer |
| Posting Date | 2026-06-15 |
| Job URL | https://www.sgdigitalbank.com/careers/ciso |
| Hiring Manager | (Not listed) |
| Company Size | 250 (approximate from LinkedIn) |
| Tier Score | 90 (base) + 0 (posted 14d ago, outside 7d window) + 0 (company <500) = **90** |
| Why Hiring Signal | Growth |
| Research Notes | Series B funded ($30M, May 2026). Building security center of excellence. Targeting ISO 27001 certification by Q3 2026. Rapid growth signals need for security infrastructure overhaul. |
| Call Status | Prospect |
| Call Angle | (To be filled after Apollo enrichment) |

### Step 5: Verification

- ✅ Tier 1 lead (CISO = highest priority)
- ✅ Clear hiring signal (growth + compliance investment)
- ✅ Detailed research notes for call prep
- ✅ URL captured exactly
- ✅ Ready for Apollo email enrichment
- ✅ Ready for call angle template (see Task 5 docs)

---

## Before/After: Airtable Row Comparison

### Before Exa Research (Minimal Data)
```
Company Name: Singapore Digital Bank Pte Ltd
Job Title: CISO
Posting Date: (unknown)
Job URL: (unknown)
Company Size: (unknown)
Why Hiring Signal: Unknown
Research Notes: (blank)
```
**Status: Can't call, insufficient info**

### After Exa Research (Rich Data)
```
Company Name: Singapore Digital Bank Pte Ltd
Job Title: Chief Information Security Officer
Posting Date: 2026-06-15
Job URL: https://www.sgdigitalbank.com/careers/ciso
Company Size: 250
Why Hiring Signal: Growth
Research Notes: Series B funded ($30M, May 2026). Building security center 
                of excellence. Targeting ISO 27001 certification by Q3 2026. 
                Rapid growth signals need for security infrastructure overhaul.
Tier Score: 90
Call Status: Prospect → (Ready for Apollo enrichment → Call Angle prep)
```
**Status: Ready to enrich and call**

---

## Troubleshooting & Edge Cases

### Issue: No Results Found for Query

**Symptom:** Exa search returns 0-2 results even though you know jobs exist.

**Possible causes:**
1. Query too specific (e.g., `Chief Information Security Officer` exact match)
2. Singapore companies post on local job boards Exa doesn't index well
3. Search term formatting (quotes, boolean operators)

**Solutions:**
1. **Broaden the query:**
   - ❌ `Chief Information Security Officer Singapore`
   - ✅ `CISO OR "VP Security" OR "Head of Security" Singapore`

2. **Include job board domains:**
   - `CISO Singapore site:linkedin.com OR site:glassdoor.com OR site:jobstreet.com`

3. **Try company-specific search:**
   - `site:company.com.sg security hiring`

4. **Search for broader signal:**
   - `Singapore security hiring 2026` (less specific, more results)

### Issue: Results Are Mostly Global, Not Singapore

**Symptom:** Exa returns CISO jobs from USA, Australia, India instead of Singapore.

**Solutions:**
1. **Always include location in query:**
   - ✅ `CISO job Singapore`
   - ❌ `CISO job opening` (too broad)

2. **Use Singapore-specific language:**
   - `CISO Singapore OR "Singapore, Singapore" OR "SG"`
   - `CISO "Singapore, Singapore"` (postal format)

3. **Filter by domain:**
   - `CISO site:sg` (Singapore domain)
   - `CISO site:.com.sg` (explicit Singapore)

4. **Exclude other regions (if needed):**
   - `CISO Singapore -Australia -"Sydney" -Melbourne`

### Issue: Old or Outdated Results

**Symptom:** Most results are from 6+ months ago; no recent postings.

**Solutions:**
1. **Add date to query:**
   - `CISO Singapore 2026` (most recent)
   - `CISO Singapore "June 2026"` (specific month)

2. **Search for "now hiring":**
   - `CISO "now hiring" Singapore 2026`
   - `security roles "currently open" Singapore`

3. **Focus on "recently posted":**
   - Exa may offer date filters in interface; use if available
   - Or search for: `CISO Singapore "posted this week"` OR `"posted 3 days ago"`

### Issue: Can't Find Company Context (Why Hiring?)

**Symptom:** Exa searches don't return growth/compliance/team signals for a company.

**Solutions:**
1. **Try alternate company names:**
   - Legal entity vs. trading name
   - Example: "DBS Bank" vs. "DBS Group Holdings"

2. **Search LinkedIn instead:**
   - `site:linkedin.com/company/[company-name] security OR CISO`
   - LinkedIn often has company news/hiring announcements

3. **Check Crunchbase for funding:**
   - `site:crunchbase.com [company-name] funding Series`

4. **Broaden the signal search:**
   - Instead of breach signal, look for "compliance" or "regulation" news
   - Not all companies announce everything publicly

5. **Accept "Unknown":**
   - If you can't find a clear signal after 5-10 min searching, mark as "Unknown" in Airtable
   - Still worth calling (Tier 1 CISO hire = signal enough)

### Issue: Found 50 Results, How Do I Prioritize?

**Symptom:** Broad query returns too many leads; don't know where to start.

**Solution: Quick Filter System**

1. **Score all 50 mentally in 10 minutes:**
   - CISO/VP titles → Keep (top 5-10)
   - Manager titles posted <7 days → Keep (next 10-15)
   - Everything else → Discard

2. **Deep dive top 10:**
   - Spend 8 min per lead on context research
   - Narrow to 5 truly hot leads

3. **Batch add to Airtable:**
   - Enter all 5 at once
   - Tier Score auto-calculates
   - Sort by Tier Score in Airtable for prioritization

4. **Follow up on discards later:**
   - If pipeline is slow, research Tier 2-3 leads
   - Reuse your research as follow-up intel

---

## How to Find Alternative Data Sources (If Exa Fails)

If Exa isn't returning what you need, here are alternative sources:

| Source | Best For | How to Use |
|--------|----------|-----------|
| **LinkedIn Jobs** | Current postings, direct contact | Search "CISO Singapore", filter by "Posted within 7 days" |
| **JobStreet.com** | Singapore-specific jobs | Search "CISO" category, location: Singapore |
| **Glassdoor** | Company reviews + job postings | Search company name, look for recent security hiring |
| **Indeed.com** | Broad job board | Search "CISO Singapore", review posting dates |
| **Company career pages** | Official jobs | Search Google: `site:company.com.sg security OR CISO` |
| **Crunchbase** | Company funding + news | Search company → look for Series funding, employee growth |
| **News sites** | Breaches, hiring announcements | Search "Singapore bank security" OR "CISO hired" |
| **LinkedIn Company pages** | Team size, hiring announcements | Search company → view "About", "Posts" tab |

**When to use alternatives:**
- Exa returns 0 results → Try LinkedIn or company career pages
- Need company funding info → Crunchbase, press releases
- Need breach/incident info → News sites, industry publications
- Need to verify job exists → Company career page (official source)

---

## Key Takeaways

1. **Exa MCP is your primary research tool** — Use it for job searches and company context
2. **Tier 1 = Tier 1** — CISO/VP roles are rare. When you find them, prioritize immediately
3. **Why matters as much as what** — Understanding hiring context (growth, compliance, breach) informs your call angle
4. **Speed: 5-10 min per company** — Set a timer. Deep research is valuable; infinite research is wasteful
5. **Batch > One-by-one** — Research 5-10 leads in sequence, then add all to Airtable
6. **Document exactly as shown** — Job titles, URLs, posting dates must be precise for Airtable scoring
7. **Move on from duds** — Skip small companies, old postings, junior roles. Stick to Tier 1 & 2
8. **Combine signals** — Growth + Recent posting + CISO title = 🔥 Hot lead

---

## Related Documentation

- **Airtable Setup:** See `docs/airtable-setup.md` for table structure and field definitions
- **Scoring Framework:** See `docs/scoring-formula.md` for Tier Score calculation and multipliers
- **Next Step: Apollo MCP Enrichment:** See `docs/apollo-mcp-guide.md` for email/phone lookup
- **Call Preparation:** See `docs/ae-workflow-guide.md` and `docs/call-angle-templates.md` for how to use your research in discovery calls

---

## Exa MCP Command Reference (Quick Lookup)

**If you need to invoke Exa MCP directly in Claude Code:**

```
Query Syntax: [search query] [location filter] [date filter] [site filter]

Examples:
- Basic search:          "CISO Singapore"
- With date:             "CISO Singapore 2026"
- With job board:        "CISO Singapore site:linkedin.com"
- Boolean OR:            "CISO OR \"VP Security\" Singapore"
- Exclude terms:         "CISO Singapore -Australia"
- Company specific:      "site:company.com.sg security hiring"
- Phrase search:         "\"Chief Information Security Officer\" Singapore"
```

For detailed Exa MCP documentation, see: https://docs.exa.ai/ (if available through Claude Code)

---

**✅ Setup complete.** You're ready to start searching for security job opportunities in Singapore.

Next step: Use this guide to find your first leads, then move to Task 4 (Apollo MCP enrichment) to get email and phone contact information.
