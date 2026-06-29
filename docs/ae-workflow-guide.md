# AE Workflow Guide: Security Hiring Research & Discovery Calls

## Overview

This is the operational playbook for Account Executives working the GTM Security Hiring Research workflow. It covers all 4 phases of turning a cold security job posting into a qualified opportunity.

**Your goal:** Convert fresh security job postings into discovery calls with decision-makers who have budget and hiring urgency.

**Key metric:** 1-2 qualified leads per day (4-5 hours of work)

**Success definition:** Security decision-maker (CISO, VP Security, Director) confirms they're hiring for a reason you can sell against (growth, compliance, post-breach recovery, or capability gap).

---

## Workflow Overview: 4 Phases

```
PHASE 1: Search & Identify (30 min)
   ↓ [Use Exa MCP to find jobs + company context]
   ↓
PHASE 2: Enrich & Verify (15 min)
   ↓ [Use Apollo MCP to get email + phone]
   ↓
PHASE 3: Prepare & Call (20 min)
   ↓ [Deep research + write call angle]
   ↓
PHASE 4: Track & Follow Up (varies)
   ↓ [Call outcomes + next steps]
   ↓
REPEAT → Next Lead
```

**Total time per lead: 60-75 minutes** (plus call time)  
**Recommended cadence: 1-2 leads per day**

---

## PHASE 1: Search & Identify (30 min per prospect)

### Objective
Find security job postings in Singapore, confirm Tier Score ≥70, understand why they're hiring, and add to Airtable with rich context.

### Step-by-Step Process

#### Step 1A: Search for Job Postings (5-10 min)

Use **Exa MCP** to find Tier-1 security job openings in Singapore.

**Why Exa?** Real-time web search, job board scraping, direct URL extraction.

**Recommended searches** (run 2-3 in sequence):

1. **Tier-1 Executive Search** (highest priority)
   ```
   CISO Singapore hiring job posting 2026 site:linkedin.com OR site:glassdoor.com OR site:indeed.com
   ```

2. **VP Security Search** (also high priority)
   ```
   "VP Security" OR "VP Information Security" OR "Head of Security" Singapore job 2026
   ```

3. **Manager Search** (if Tier-1 sparse)
   ```
   "Security Manager" OR "Security Operations Manager" OR "Security Director" Singapore job 2026
   ```

**What to look for:**
- ✅ Job title: CISO, VP, Director, Manager (NOT individual contributor)
- ✅ Posted date: Within last 14 days (fresh signal)
- ✅ Company: 100+ employees (has budget)
- ✅ Clear job description (not spam)

**Red flags to skip:**
- ❌ Generic "Security Engineer" role
- ❌ Posted 60+ days ago
- ❌ Startup with <50 employees
- ❌ No company website

#### Step 1B: Capture Job Posting Data (3-5 min per prospect)

For each promising result, extract and record:

| Data Point | Where to Get | Example | Note |
|------------|-------------|---------|------|
| **Company Name** | Job posting or website | "DBS Bank Ltd" | Use legal/official name |
| **Job Title** | Job posting heading | "Chief Information Security Officer" | Exact title from posting |
| **Job URL** | Exa result or posting | `https://careers.dbs.com/ciso-2026` | Full https:// URL |
| **Posting Date** | Job metadata | 2026-06-22 | Posting date, not discovery date |
| **Hiring Manager** | Job posting or LinkedIn | "Jane Smith" or "Hiring Team" | If listed; use generic if not |
| **Company Size** | Company website or LinkedIn | 1,200 | Approx. employees; ok to estimate |

**Capture tool:** Use a scratch pad or temporary note to gather this. You'll enter into Airtable in Step 1D.

#### Step 1C: Research Company Context — WHY Are They Hiring? (10-15 min per prospect)

This is the most important research phase. Understanding the hiring driver informs your entire call angle.

Use **Exa MCP** to search for these signals:

**Search 1: Growth Signal**
```
[Company Name] funding Series A OR Series B OR expansion OR raised OR headcount growth 2025 2026
```

**What you're looking for:**
- Recent funding announcements
- New office openings or geographic expansion
- New product launches
- Headcount growth announcements

**Example finding:** "DBS Bank announced $500M Series B in Q2 2026, expanding tech team by 50%"

**Signal strength:** 🔥 STRONG — Growing companies need security infrastructure scaling

---

**Search 2: Compliance Signal**
```
[Company Name] PDPA OR compliance OR ISO 27001 OR SOC 2 OR regulation Singapore 2025 2026
```

**What you're looking for:**
- New regulatory requirements (PDPA, ISO, SOC 2)
- Compliance certifications or announcements
- Legal/regulatory news
- Data privacy commitments

**Example finding:** "Company announces ISO 27001 certification target by Q4 2026"

**Signal strength:** 🔥 STRONG — Compliance-driven hiring shows executive mandate + budget

---

**Search 3: Breach or Incident Signal**
```
[Company Name] breach OR incident OR hack OR security alert OR "cybersecurity incident" 2025 2026
```

**What you're looking for:**
- Publicized security incidents
- Breach announcements or disclosures
- Vulnerability discoveries
- Post-incident hiring announcements

**Example finding:** "TechCorp Singapore disclosed data breach affecting 50K customers; CVE published"

**Signal strength:** 🔥🔥 VERY STRONG — Post-breach hiring = high urgency + executive focus + dedicated budget

---

**Search 4: Leadership/Team Signal** (optional, for confirmation)
```
site:linkedin.com "[Company Name]" CISO OR "VP Security" OR "Head of Security" hired OR joined 2025 2026
```

**What you're looking for:**
- New security leaders joining
- Executive hires
- Leadership changes in security function

**Example finding:** "John Smith, former CISO of Bank X, joins DBS as Head of Security"

**Signal strength:** ⭐ MODERATE — Confirms investment, shows serious intent

---

**Synthesis: Identify Primary WHY Hiring Signal**

After 2-3 searches, pick ONE primary signal:

1. **Growth** – Company is expanding (new funding, new markets, new products)
2. **Compliance** – Company is responding to regulatory mandate (PDPA, ISO, SOC 2)
3. **Breach Recovery** – Company is recovering from publicized incident
4. **Unknown** – No clear signal found after 10-15 min of research (still worth calling!)

**Important:** If you find BOTH growth + compliance signals, pick the STRONGER one. (Growth + Compliance = Growth, because growth is the driver; Compliance is the consequence.)

**If no signal found:** Mark as "Unknown" and still proceed. Tier-1 roles (CISO/VP) are valuable regardless.

#### Step 1D: Calculate Tier Score & Verify ≥70 (2 min)

Before adding to Airtable, manually verify the Tier Score will be ≥70.

**Quick Tier Score Calculator:**

```
Base Score (by job title):
  CISO / VP Security / Head of Security = 90 points
  Director / Manager = 75 points
  Architect / Senior Engineer = 60 points
  Individual Contributor = 40 points

Recency Bonus:
  Posted 0-6 days ago = +10 points
  Posted 7+ days ago = 0 points

Company Size Bonus:
  500+ employees = +5 points
  <500 employees = 0 points

TOTAL = Base + Recency + Size
```

**Scoring examples:**

| Scenario | Base | Recency | Size | Total | Tier | Action |
|----------|------|---------|------|-------|------|--------|
| CISO, 3 days old, 800 emp | 90 | +10 | +5 | 105 | 1 | ✅ ADD TO AIRTABLE |
| Manager, 15 days old, 200 emp | 75 | 0 | 0 | 75 | 2 | ✅ ADD TO AIRTABLE |
| Security Architect, 2 days, 150 emp | 60 | +10 | 0 | 70 | 2 | ✅ ADD TO AIRTABLE (borderline) |
| Engineer, 45 days old, 80 emp | 40 | 0 | 0 | 40 | 4 | ❌ SKIP |

**Decision rule:**
- **Score ≥90:** Add immediately (Tier 1 hot lead)
- **Score 70-89:** Add and prioritize (Tier 2 good lead)
- **Score <70:** Skip for now; add to backlog only if pipeline is slow

#### Step 1E: Add to Airtable (5 min)

Log into your **Airtable SecurityLeads** base and create a new record with:

**Required fields:**
1. **Company Name** – Exact legal name
2. **Job Title** – From posting (Single Select)
3. **Posting Date** – Date job was posted
4. **Job URL** – Full https:// URL
5. **Why Hiring Signal** – Growth / Compliance / Breach Recovery / Unknown
6. **Company Size** – Employee count (approx. ok)
7. **Call Status** – Set to "Prospect" (not yet contacted)

**Optional fields (fill if you have the data):**
- Hiring Manager
- Research Notes – 2-3 sentences on what you learned

**Example Airtable row:**

| Field | Value |
|-------|-------|
| Company Name | DBS Bank Ltd |
| Job Title | Chief Information Security Officer |
| Posting Date | 2026-06-22 |
| Job URL | https://careers.dbs.com/ciso-2026 |
| Hiring Manager | (Not listed) |
| Company Size | 2,800 |
| Why Hiring Signal | Growth |
| Research Notes | Series B funded 2026. Expanding tech team across APAC. ISO 27001 certification in progress. |
| Call Status | Prospect |
| Tier Score | (Auto-calculated: 90) |

**Note:** Tier Score will auto-calculate as soon as you fill Job Title and Company Size. Check it matches your manual calculation.

---

### Phase 1 Checklist

Before moving to Phase 2, verify:

- [ ] Found job posting on 1-2 reliable job boards (LinkedIn, Glassdoor, Indeed, or company site)
- [ ] Extracted exact job title and company name
- [ ] Researched 2-3 "why hiring" signals using Exa
- [ ] Identified primary Why Hiring Signal (Growth / Compliance / Breach / Unknown)
- [ ] Calculated Tier Score ≥70 (if <70, skip this prospect)
- [ ] Added record to Airtable with all key fields filled
- [ ] Tier Score formula auto-calculated correctly
- [ ] Research Notes capture your key findings in 2-3 sentences

**Time spent:** 30 min per prospect

**If spent >40 min on one prospect:** STOP and move to next. Diminishing returns on research.

---

## PHASE 2: Enrich & Verify (15 min per prospect)

### Objective
Get verified email and phone for the hiring decision-maker, update company size in Airtable, and confirm Tier Score is still ≥70 with all data.

### Step-by-Step Process

#### Step 2A: Identify Decision-Maker Contact (3 min)

From the job posting and your research, identify WHO to contact. Options in priority order:

1. **Hiring Manager Name** (if mentioned in posting) – "Apply directly to: John Smith"
2. **Job Title Poster** (implicit from job level) – CISO → likely reports to CFO or CRO; contact CISO directly
3. **Company Recruiting Team** – "Apply via Talent Acquisitions" → contact recruiting/talent team

**Examples:**

| Job Level | Contact Priority |
|-----------|------------------|
| CISO opening | Contact CISO directly (if hiring from outside), OR CFO/CRO if building new function |
| VP Security opening | Contact CFO/CRO or current VP of equivalent (if lateral hire) |
| Security Director opening | Contact CISO or VP Security (if one exists) |
| Manager opening | Contact Director or Manager level above |

**Tip:** LinkedIn search for company + title gives you potential names and email hints.

#### Step 2B: Use Apollo MCP to Enrich Contact (8-10 min)

Use **Apollo MCP** to look up verified email and phone for the decision-maker.

**Apollo Search** (in Claude Code):

```
Query: [First Name] [Last Name] [Company Name] Singapore
or
Query: [Job Title] [Company Name] Singapore (if name unknown)
```

**Example queries:**
- `"John Smith" "DBS Bank Ltd" Singapore`
- `CISO "DBS Bank Ltd" Singapore`
- `Chief Information Security Officer "DBS Bank Ltd"`

**What Apollo returns:**

```
Name: John Smith
Title: Chief Information Security Officer
Company: DBS Bank Ltd
Location: Singapore, Singapore
Email: john.smith@dbs.com (Confidence: High)
Phone: +65 6878-XXXX (Confidence: Medium)
LinkedIn: linkedin.com/in/johnsmith
```

**Email confidence levels:**
- **High:** Apollo found it in multiple sources (LinkedIn, company directory, email signature)
- **Medium:** Found in one source or pattern-matched
- **Low/Unverified:** Use with caution; may bounce

**Phone confidence levels:**
- **High:** Direct line from company directory or LinkedIn
- **Medium:** Office number (may route through receptionist)
- **Low:** Found in limited sources

**If Apollo finds multiple results:**
- Pick the person with the exact job title you're seeking
- If multiple CISOs: prioritize by seniority or recent LinkedIn activity
- If hiring manager listed in job posting: prioritize that person

**If Apollo finds NO results:**
- Try variant names: John vs. Jon, Smith vs. Smythe
- Try title-based search: "VP Security" instead of name
- Try company variations: DBS vs. "DBS Group" vs. "DBS Bank Limited"
- If still nothing: Leave Email/Phone blank and research alternatives (LinkedIn, company website, email guessing)

**Apollo Tip:** Batch enrichment is faster. If you have 5 prospects, look them all up at once instead of one-by-one. Apollo can return results for multiple queries together.

#### Step 2C: Update Airtable with Contact Info (2 min)

Return to your Airtable record and fill:

- **Email** – Verified email address
- **Phone** – Phone number (include country code: +65 XXXX XXXX)

**Example:**

| Field | Value |
|-------|-------|
| Email | john.smith@dbs.com |
| Phone | +65 6878-1234 |

**If you found no email:**
- Leave blank for now
- In Phase 3, you'll use LinkedIn messaging or cold outreach techniques
- Update Airtable with contact info if you find it later

#### Step 2D: Verify Tier Score Still ≥70 (1 min)

Now that Airtable has complete data (Company Size, Job Title, Posting Date), check Tier Score formula:

- **Tier Score ≥90:** 🔥 Tier 1 hot lead — prioritize this week
- **Tier Score 70-89:** ⭐ Tier 2 good lead — prioritize within 2 weeks
- **Tier Score <70:** 📋 Tier 3/4 — research later if pipeline needs filling

If score dropped below 70, you can still work it (Tier-1 CISO is always worth calling), but deprioritize if time-constrained.

---

### Phase 2 Checklist

Before moving to Phase 3, verify:

- [ ] Identified decision-maker name (hiring manager or role-based)
- [ ] Searched Apollo MCP for contact info
- [ ] Found or attempted to find: Email address + Phone number
- [ ] Updated Airtable Email and Phone fields
- [ ] Rechecked Tier Score with all data complete
- [ ] Confirmed Tier Score ≥70 (or decision to work it anyway)

**Time spent:** 15 min per prospect

**If spent >20 min enriching:** Apollo isn't finding results; move on and use alternative contact methods in Phase 3.

---

## PHASE 3: Prepare & Call (20 min per prospect)

### Objective
Deep-dive company research, write personalized call angle using templates, prepare discovery message, and make the call.

### Step-by-Step Process

#### Step 3A: Deep Dive Research — Expand "Why Hiring Signal" (8-10 min)

You identified a primary WHY signal in Phase 1. Now add specific details that will personalize your call.

Use **Exa MCP** or LinkedIn/company website to research:

**If Growth Signal:**
- What exactly is the company expanding? (New market? New product line? New customer segment?)
- When did funding happen? How much? What's the growth trajectory?
- Who leads the expansion (CEO, CTO, VP Product)?
- Example research: "Series B $30M raised May 2026. Expanding APAC presence. Opening Singapore tech hub with 50 new hires. CTO leading product roadmap."

**If Compliance Signal:**
- What specific regulation or standard? (PDPA? ISO 27001? SOC 2? SOX?)
- What's the deadline? (Q3 2026? End of 2026?)
- Is company proactive or reactive? (Regulation mandated vs. company choosing)
- Example research: "PDPA enforcement ramping up in Singapore mid-2026. Company targeting compliance by Q2 2026. New Data Protection Officer hired."

**If Breach Recovery Signal:**
- When was incident? How public?
- How many customers/records affected?
- What's the recovery narrative? (Strengthening security? Hiring team? New CISO?)
- Example research: "June 2026 disclosed breach affecting 100K customer records. Hired external IR firm. Now hiring CISO to rebuild security function."

**If Unknown Signal:**
- Can't find specific signal, but Tier-1 role = valuable
- Research company's general security posture (any public compliance info?)
- Research company's growth stage (startup vs. scale-up vs. enterprise?)
- Example research: "Late-stage fintech. No recent funding news, but strong growth in customer base. Proactive on compliance (ISO 27001)."

**Sources for deep research:**
1. Exa MCP (broad queries)
2. LinkedIn company page (recent posts, hiring announcements)
3. Company website (about page, blog, press releases)
4. Crunchbase (funding history)
5. News sites (industry publications)

#### Step 3B: Research Hiring Manager Background (3-5 min)

Find out who you're calling:

- **Current role & company:** Is this person building a new function or inheriting a team?
- **Background:** Previous companies, titles, experience level?
- **LinkedIn activity:** How recent? Any security-related posts?
- **Common interests:** Any security conferences, certifications, publications?

**Where to research:**
- LinkedIn profile (if you have their email, search by email or name)
- Company website (security team page)
- Past company announcements

**Why this matters:** Personalization on the call. "I saw you came from [Company] where you led [security initiative]" → Instant credibility.

**Example:** "John Smith, CISO at DBS, spent 5 years at Citibank leading compliance. Very security-first background. DBS blog shows he's focused on ISO 27001 certification."

#### Step 3C: Research Company's Security Posture (2-3 min)

Quick scan of what they publicly say about security:

- **Public compliance claims:** Do they mention ISO 27001, SOC 2, GDPR?
- **Security blog/messaging:** Do they post security content?
- **Security team size:** How many people on LinkedIn claim to work in security at this company?
- **Maturity signals:** Do they have a security center of excellence, security training, bug bounty program?

**Why this matters:** Call angle personalization. If they're "just getting started" on security, different opening than if they're "scaling a mature program."

**Sources:** Company website, LinkedIn company page, security team searches.

#### Step 3D: Write Personalized Call Angle (5-7 min)

Use the **Call Angle Templates** (see separate document: `call-angle-templates.md`) matched to your WHY HIRING SIGNAL:

1. **Growth Signal** → Use Growth Signal template
2. **Compliance Signal** → Use Compliance Signal template
3. **Breach Recovery Signal** → Use Breach Recovery template
4. **Unknown Signal** → Use Generic template

**Call Angle structure:**

```
OPENING (30-45 sec):
   - Name and company
   - Acknowledge their hiring or signal
   - One-liner on why you're calling

DISCOVERY GOAL (15 sec):
   - What you want to learn on this call
   - Frame as mutual benefit ("I want to understand...")

DISCOVERY QUESTIONS (10-15 min):
   - 3-5 open-ended questions based on your research
   - Listen actively; adjust based on responses

LISTEN & PROBE (10-15 min):
   - Find the pain point
   - Understand current posture
   - Identify what's driving urgency

SUGGEST (if appropriate, 5-10 min):
   - Light mention of how you might help
   - NOT a hard sell; "Could be a fit if X"

CLOSE (2 min):
   - "Should we schedule 20 min next week to dig deeper?"
   - Get their calendar invite or next steps

TOTAL CALL: 30-45 minutes (first conversation)
```

**Write 1-paragraph opening for your specific lead:**

Example (Growth Signal, DBS Bank):

> "Hi John, it's [Your Name] from [Your Company]. I noticed DBS is expanding aggressively across APAC with the Series B you announced, and I saw the CISO opening on your careers page. That's exactly what I talk to Security leaders about — when companies scale fast, there's always a gap between infrastructure and security readiness. I'm not trying to sell anything today, but I thought it was worth a quick call to understand where you're at and what the new hire's mandate is. Do you have 20 minutes sometime this week?"

#### Step 3E: Prepare First Outreach Message (2 min)

Compose your first outreach via email or LinkedIn:

**If you have VERIFIED EMAIL:**

```
Subject: Quick question about your CISO opening @ DBS

Hi John,

I noticed DBS is hiring a CISO as you scale the APAC tech hub 
(congrats on the Series B, by the way). 

That's exactly what I work on—helping fast-growing security 
teams navigate the security/infrastructure gap when things 
move fast.

Would you have 20 minutes this week for a quick chat? No 
pitch—just want to understand your mandate and see if we 
should talk more.

[Your Name]
[Your Title]
[Your Company]
[Your Phone]
```

**If you DON'T have email but have name:**

```
LinkedIn DM:

Hi John—

I saw DBS is expanding aggressively and hiring a CISO. As you 
bring on new security leadership, there's a lot to think about 
on the infrastructure/security alignment side.

Would love to grab 20 min to compare notes. I work with CISOs 
and Security VPs through similar scaling phases.

Available Tue/Wed if that works for you.

[Your Name]
```

**If you have PHONE:**

Use the phone for initial outreach (warmer than email, but less written record). Reference your outreach channel:

"Hi John, it's [Name] with [Company]. I sent you an email about the CISO role at DBS. Do you have 5 minutes?"

#### Step 3F: Make the Call (5-10 min)

**Before calling:**
- [ ] Have Airtable record open
- [ ] Have call angle written and in front of you
- [ ] Have specific company research notes ready
- [ ] Have calendar open to suggest next meeting time

**During the call:**
- Use your opening (personalized, not scripted)
- Listen more than talk (aim for 70/30 ratio)
- Probe on the pain point (use discovery questions from template)
- Take notes on outcomes (add to Research Notes field)
- Suggest next step if there's interest

**Call outcomes:**
- **Interested:** Schedule 30-min discovery, update Call Status to "Qualified"
- **Curious but not ready:** Agree to follow-up in 2 weeks, update Call Status to "Called"
- **Not interested or wrong person:** Mark Call Status to "Lost", note reason
- **Voicemail/No answer:** Mark Call Status to "Called", note that you left VM

---

### Phase 3 Checklist

Before and after the call, verify:

- [ ] Completed deep dive research on WHY signal (expansion details, compliance deadline, breach timeline, etc.)
- [ ] Researched hiring manager background (LinkedIn, past experience, relevant skills)
- [ ] Researched company's security posture and maturity
- [ ] Wrote personalized opening (1 paragraph, 30-45 seconds)
- [ ] Matched call angle template to WHY signal type
- [ ] Prepared discovery questions (3-5 open-ended questions)
- [ ] Composed outreach message (email or LinkedIn)
- [ ] Made call or scheduled call
- [ ] Updated Airtable with call outcome (Call Status, Call Angle, Research Notes)

**Time spent:** 20 min research + 30-45 min call = ~60 min total for Phase 3

**If you can't get a hold of them:** Leave voicemail with reference to email, note in Airtable, try again in 3-5 days.

---

## PHASE 4: Track & Follow Up

### Objective
Log outcomes, update prospect status, set next actions, and manage pipeline.

### Step-by-Step Process

#### Step 4A: Update Call Status (2 min)

After every call or outreach attempt, update **Call Status** in Airtable:

| Status | Condition | Next Action |
|--------|-----------|------------|
| Prospect | Initial record created, not yet contacted | Phase 1-3 |
| Researched | Researched but not contacted | Phase 3 (outreach) |
| Called | Reached out (call, email, VM left) | Follow up in 3-5 days |
| Qualified | Confirmed interest; decision-maker engaged; 30-min meeting scheduled | Prep for discovery meeting |
| Won | Signed deal or partnership | Close & celebrate |
| Lost | Not interested, wrong fit, company declined | Note reason; potential future revisit |

#### Step 4B: Log Outcomes in Research Notes (3 min)

Update Research Notes field with:

**If call happened:**
```
CALLED [Date]: Spoke with [Name]. 
  - Pain point: [What they're struggling with]
  - Current state: [What their security posture is]
  - Timeline: [When they need to decide/hire]
  - Next step: [You'll call back, they'll call you, meeting scheduled]
  - Key quote: "[Something they said that resonates]"
```

**If voicemail left:**
```
VM LEFT [Date]: Called [Name], left message about CISO role and Series B growth. 
  - Mentioned: [Specific reference to their company/role]
  - Next: Will try again [Date] or email follow-up
```

**If email sent:**
```
EMAIL SENT [Date]: Outreach to [Name] via [email/LinkedIn].
  - Angle: [Which template you used]
  - Key message: [Main reason for reaching out]
  - Next: Waiting for response; will follow up [Date]
```

#### Step 4C: Set Next Action & Date (1 min)

Update **Next Action** field with specific next step:

Examples:
- "Follow up via email Friday 2026-06-28"
- "Call back Tuesday, June 30 @ 10am"
- "Send meeting prep document before discovery call"
- "Research company's incident timeline further"
- "Escalate to sales leader—customer ready to close"

**Set a specific date.** Vague ("follow up soon") leads to dropped leads.

#### Step 4D: Manage Pipeline (5 min per week, not per prospect)

Once per week, review your Airtable and:

1. **Sort by Call Status:**
   - How many "Qualified"? (These should be your priority)
   - How many "Called"? (Follow up on aged ones)
   - How many "Prospect"? (Need to move to Phase 3)

2. **Check "Next Action" dates:**
   - Any overdue? (Do them today)
   - Any this week? (Schedule them)

3. **Rebalance pipeline:**
   - Need more prospects? Go back to Phase 1 (Exa searches)
   - Need to close deals? Focus on "Qualified" leads
   - Too many "Lost"? Analyze: Were you targeting right Tier? Right signal?

#### Step 4E: Follow-Up Cadence (based on status)

Once you've called a prospect, use this follow-up plan:

| Status | Initial Outreach | Follow-Up 1 | Follow-Up 2 | Follow-Up 3 |
|--------|------------------|------------|------------|------------|
| Called (interested) | Day 0 | +3 days | +7 days | +14 days |
| Called (curious) | Day 0 | +5 days | +10 days | +30 days (drop) |
| Called (not ready) | Day 0 | +2 weeks | +1 month | +90 days |
| Voicemail left | Day 0 (VM) | +3 days (email) | +7 days (call) | +14 days (drop) |

**Example:**
- Day 1 (Monday): Called John Smith, left voicemail
- Day 4 (Thursday): Send email follow-up with specific value prop
- Day 8 (Monday): Call again, reference your previous attempts
- Day 15+ (Next Monday): If still no response, move to backlog

---

### Phase 4 Checklist

- [ ] Updated Call Status based on actual outcome
- [ ] Logged call outcomes (or voicemail/email attempt) in Research Notes
- [ ] Set specific Next Action with date
- [ ] Created follow-up reminders for non-responses
- [ ] Reviewed pipeline once per week for bottlenecks
- [ ] Moved "Qualified" leads to discovery meeting prep

---

## Tier Score Reference Table

Quick lookup for lead prioritization:

| Tier | Score Range | Job Title Examples | Priority | When to Call |
|------|-------------|-------------------|----------|------------|
| **Tier 1: Executive** | 90-105 | CISO, VP Security, Head of Security, Chief Security Officer | 🔥 This week | Immediately after enrichment |
| **Tier 2: Management** | 70-89 | Security Director, Security Manager, Compliance Manager | ⭐ Next 2 weeks | Within 5 business days |
| **Tier 3: Senior Technical** | 60-79 | Security Architect, Senior Security Engineer | 💼 Backlog | If pipeline slow |
| **Tier 4: Individual Contributor** | 40-59 | Security Engineer, SOC Analyst | 📋 Low priority | Only if reaching quota |

**Decision rule:** Tier Score <70 = Skip (unless searching for volume). Tier Score ≥70 = Work it.

---

## Tier Strategy: How to Prioritize

### If you have limited time (2-3 hours/day):

1. **Prioritize Tier 1 (score 90+):** CISO/VP roles, recent postings, big companies
2. **Only add Tier 2 (score 70-89) if:** Posted within 7 days AND clear Why Hiring Signal
3. **Skip Tier 3 & 4** unless you have time and pipeline needs filling

### If you have more time (5-6 hours/day):

1. **Deep dive on Tier 1:** Detailed research, multiple call attempts, personalized angles
2. **Add Tier 2:** Work 1-2 per day alongside Tier 1
3. **Tier 3 as backlog:** Only if you've exhausted Tier 1 & 2 in market

### If you're filling a new pipeline (first month):

1. **Broad search:** Tier 1, 2, and 3 to build lead list
2. **Quick score:** Discard Tier 4 and very aged postings
3. **Batch research:** 10-15 prospects in Phase 1-2, then call top 5

---

## Tools Checklist

| Tool | Used in | Purpose | Status |
|------|---------|---------|--------|
| **Exa MCP** | Phase 1 | Job search + company research | ✅ See `docs/exa-mcp-guide.md` |
| **Apollo MCP** | Phase 2 | Contact enrichment (email/phone) | ✅ See `docs/apollo-mcp-guide.md` |
| **Airtable** | All phases | Lead tracking + scoring | ✅ See `docs/airtable-setup.md` |
| **LinkedIn** | Phase 3 | Hiring manager research + outreach | ✅ Manual use |
| **Company websites** | Phase 1 & 3 | Company info + security posture | ✅ Manual use |

---

## Common Mistakes to Avoid

### ❌ Mistake 1: Skipping Phase 1 Research
**Problem:** Calling without understanding why they're hiring. ("So why are you hiring?")
**Impact:** Weak opening, prospect skeptical, lower conversion
**Fix:** Always spend 10-15 min on company research before calling.

---

### ❌ Mistake 2: Calling Too Soon
**Problem:** Reaching out before Tier Score is ≥70 or without enriched contact info.
**Impact:** Low contact quality, bad data (wrong person, bad phone), wasted call
**Fix:** Don't call until you've completed Phase 2 (Apollo enrichment).

---

### ❌ Mistake 3: Not Recording Data Exactly
**Problem:** Typing "CISO" instead of exact title from posting; wrong company name spelling.
**Impact:** Tier Score formula fails; can't find contact; data integrity breaks
**Fix:** Copy-paste titles and company names directly from source; don't paraphrase.

---

### ❌ Mistake 4: Generic Opening
**Problem:** "Hi John, I'm calling about security." Sounds like every other sales call.
**Impact:** Immediate rejection or "not interested"
**Fix:** Reference their specific company, role, signal. "I saw your Series B and the CISO hire..."

---

### ❌ Mistake 5: Pitching Too Soon
**Problem:** Launch into product features on first call. ("Our tool does...")
**Impact:** Prospect is defensive; call ends; no follow-up
**Fix:** First call is discovery. Listen 70%, talk 30%. Ask questions. No pitch.

---

### ❌ Mistake 6: Not Following Up
**Problem:** Call once, no answer. Never follow up again.
**Impact:** Missed opportunities; didn't give prospect multiple chances to engage
**Fix:** Plan 3-4 follow-ups over 30 days. Use email, phone, and LinkedIn.

---

### ❌ Mistake 7: Confusing "Why Hiring Signal"
**Problem:** Marking a prospect as "Growth" when they're really "Compliance" driven.
**Impact:** Wrong call angle; weak personalization; lower conversion
**Fix:** Research multiple signals; pick the PRIMARY driver. Growth + Compliance? Pick Growth.

---

### ❌ Mistake 8: Spending Too Long on Bad Leads
**Problem:** Researching a Security Analyst role at a 30-person startup for 45 min.
**Impact:** Wasted time; could've worked 3-4 hot leads instead
**Fix:** Phase 1 should be ~30 min per prospect, max. If not progressing, move on.

---

## When to Move On from a Prospect

**Stop pursuing and mark "Lost" if:**

1. **No contact info found after 2 attempts** (email + phone call)
   - Try one more email, then move on
   - Exception: Tier 1 (CISO/VP) with no contact = keep trying (call their office main line)

2. **Reached prospect 2-3 times with no response**
   - After VM + email + second call, mark "Lost"
   - Exception: If "called back later" on their own, they're interested

3. **Prospect says "not interested" or "not the right time"**
   - If "not the right time," schedule follow-up in 30-60 days
   - If "not interested," update Call Status to "Lost" + note reason

4. **Job is confirmed filled**
   - They hired already; move on
   - Note: "Position filled, 2026-06-25"

5. **Company is bad fit** (e.g., post-incident but hostile to security investment)
   - Move on. "Lost - bad fit"

6. **Tier Score actually <70** and you're short on time
   - Focus on Tier 1 & 2 first
   - Come back to Tier 3 if pipeline needs filling

**Reactivation:** Once per quarter, review "Lost" leads. If company is now hiring again (new posting), you can restart outreach.

---

## Success Metrics & Definitions

### What counts as a GOOD CALL?

✅ **Qualified Call:**
- Prospect answered or called back
- You confirmed they're the decision-maker OR they directed you to the right person
- They confirmed hiring signal and timeline
- You scheduled a follow-up meeting (discovery, demo, etc.)
- They showed genuine interest (not "maybe later")

⭐ **OK Call:**
- Prospect answered
- They're evaluating the role/timeline (but not quite ready to talk)
- They asked you to follow up next month
- No immediate disqualification

❌ **Poor Call:**
- Wrong person (had to transfer)
- Prospect was hostile or dismissive
- You talked more than listened
- No clear next step

### What's a healthy pipeline?

- **At any time:** 2-3 "Qualified" leads (scheduled for discovery this week)
- **Weekly:** 5-10 new prospects in Phase 1-2 (research phase)
- **Daily:** 1-2 calls (Phase 3)
- **Monthly:** 1-2 "Won" outcomes (closed deals)

---

## Example: End-to-End Workflow

Let's walk through one prospect from search to call.

### Scenario
You're researching Singapore fintech companies. You find a CISO opening at a Series B-funded company.

### Phase 1: Search & Identify (30 min)

**Step 1A:** Exa search returns:
```
Title: Chief Information Security Officer
Company: TechShield Singapore Pte Ltd
URL: https://careers.techshield.sg/ciso-2026
Posted: 2026-06-22 (5 days ago)
```

**Step 1B:** Extract data:
- Company: TechShield Singapore Pte Ltd
- Title: Chief Information Security Officer
- URL: Saved
- Posted: 2026-06-22
- Size: ~800 (from LinkedIn)

**Step 1C:** Research "why hiring":
- Search: "TechShield Singapore" Series B
- Finding: "TechShield raises $25M Series B, expanding APAC team by 100"
- Search: "TechShield Singapore" security breach
- Finding: "Post-incident hiring focus on security infrastructure (April 2026 incident, client data exposed)"
- PRIMARY SIGNAL: Breach Recovery (incident recovery + hiring CISO to rebuild)

**Step 1D:** Calculate Tier Score:
```
Base: 90 (CISO)
Recency: +10 (5 days)
Size: +5 (800 emp)
Total: 105 ✅
```

**Step 1E:** Add to Airtable:
- All fields filled
- Call Status: Prospect
- Why Hiring Signal: Breach Recovery
- Research Notes: "Series B funded May 2026. April 2026 incident affecting customer data. CISO role newly created to rebuild security function. Strong mandate + budget signal."

---

### Phase 2: Enrich & Verify (15 min)

**Step 2A:** Identify decision-maker: Job posting doesn't list hiring manager. CISO role = will report to CEO/CFO. Try CEO first.

**Step 2B:** Apollo search:
```
Query: CEO TechShield Singapore
Result: Sarah Ng, CEO, TechShield Singapore
Email: sarah.ng@techshield.sg
Phone: +65 6789-1234
```

Secondary search:
```
Query: CISO TechShield Singapore
Result: (no CISO yet—that's why they're hiring)
Try: VP Engineering or VP Product (likely stakeholder on security hiring)
Result: Marcus Chen, VP Engineering, TechShield
Email: marcus.chen@techshield.sg
Phone: +65 6789-5678
```

**Step 2C:** Update Airtable:
- Email: marcus.chen@techshield.sg (VP Engineering, more technical, likely involved in CISO hire)
- Phone: +65 6789-5678

**Step 2D:** Verify Tier Score: Still 105 ✅

---

### Phase 3: Prepare & Call (20 min + call time)

**Step 3A:** Deep dive research on Breach Recovery signal:
- Exa search: "TechShield Singapore" "April 2026" incident
- Finding: Customer data breach, 50K records. Public disclosure, regulatory investigation ongoing.
- Finding: Company hired external IR firm; completed incident response.
- Finding: Now hiring CISO to overhaul security infrastructure and compliance program.
- Key detail: PDPA enforcement likely = urgency on compliance rebuilding

**Step 3B:** Research Marcus Chen (VP Eng):
- LinkedIn: VP Engineering at TechShield for 2 years
- Background: Previously at Google Cloud, led infrastructure security projects
- Activity: Posted about cloud security architecture, ISO 27001
- Signal: Security-savvy, likely driving CISO search on technical side

**Step 3C:** Company security posture:
- Website: Public blog post about "rebuilding trust post-incident"
- No current ISO 27001 (post-incident, they're working toward it)
- Small security team (~3 people before incident; rebuilding)
- Maturity: Early-stage security program, but getting serious now

**Step 3D:** Write personalized opening (Breach Recovery template):

> "Hi Marcus, it's [Your Name] from [Your Company]. I noticed TechShield's April incident and your CISO search—which is exactly the kind of security rebuilding work I help with. I'm not trying to sell anything, but I thought it might be worth a quick chat about how you're approaching the rebuild, what the new CISO's mandate is, and where the biggest gaps are. Do you have 20 minutes this week?"

**Step 3E:** Prepare email:

```
Subject: Quick thought on your CISO hire + security rebuild

Hi Marcus,

I noticed TechShield's incident recovery and the CISO opening. 
As someone who went through infrastructure security work at Google, 
you probably understand the challenge: how to rebuild quickly 
without compromising quality.

That's exactly what I help with—Security leaders managing recovery 
and capability building at the same time.

Would you have 20 minutes this week to compare notes? No pitch—
just want to understand your mandate and see if we should keep 
talking.

[Your Name]
[Phone]
```

**Step 3F:** Make the call:
- Called Marcus's number
- Reached directly (lucky!)
- Opened with personalized reference to incident + Google background
- Listened: Marcus confirmed CISO reporting to him; mandate is to rebuild trust, implement ISO 27001, overhaul incident response
- Probed: Asked about timeline (Q3 2026 for core rebuild), team structure (expanding to 5-person team), and biggest gap (lack of security architecture)
- Suggested: "Sounds like the architecture piece is critical. We help new security teams structure for scale. Should we schedule 30 minutes next week to dig into that?"
- Closed: Scheduled 30-min call for 2026-06-30

---

### Phase 4: Track & Follow Up

**Step 4A:** Updated Call Status: Qualified (confirmed interest, meeting scheduled)

**Step 4B:** Updated Research Notes:
```
CALLED 2026-06-26: Spoke with Marcus Chen (VP Eng, decision-maker on CISO hire).
  - Mandate: Rebuild trust post-incident. ISO 27001 by Q3 2026. Expand to 5-person team.
  - Pain point: Lack of security architecture framework. Current team is tactical, not strategic.
  - Timeline: Hiring CISO by July; want to have core policies/architecture by end of Q3.
  - Interested in: "How to structure security program for scale and audit readiness"
  - Next: Discovery call scheduled 2026-06-30 @ 2pm SGT to discuss architecture approach.
```

**Step 4C:** Set Next Action: "Prep discovery call for Jun 30; prepare 1-pager on security architecture approach"

---

### Result

✅ Converted from "Prospect" → "Qualified" → Discovery scheduled  
✅ High-value lead (Tier 1: 105 score)  
✅ Clear pain point identified (security architecture)  
✅ Decision-maker engaged (Marcus Chen)  
✅ Next meeting confirmed  

**This prospect is now a qualified opportunity ready for your discovery call.**

---

## Summary & Quick Reference

### 4-Phase Workflow at a Glance

| Phase | Time | Focus | Tools | Deliverable |
|-------|------|-------|-------|------------|
| **1: Search & Identify** | 30 min | Find jobs, research why hiring | Exa MCP, Airtable | Airtable record with Why signal + Tier Score |
| **2: Enrich & Verify** | 15 min | Get contact info, verify Tier Score | Apollo MCP, Airtable | Email + Phone in Airtable |
| **3: Prepare & Call** | 20 min + call | Research deep, write angle, call | LinkedIn, company site, Call Templates | Discovery call scheduled |
| **4: Track & Follow Up** | Varies | Update pipeline, set next actions | Airtable | Call Status updated, follow-up planned |

### Weekly Cadence

- **Monday-Thursday:** Run 1-2 leads through Phases 1-3 daily (aim for 1-2 calls/day)
- **Friday:** Admin + pipeline review; check "Qualified" leads; plan next week

### Success Metrics

- Target: 2-3 calls per week → 4-6 leads per month to "Qualified" → 1-2 deals per quarter
- Conversion by tier: Tier 1 = 40-60% conversion; Tier 2 = 20-30%

---

## Related Documentation

- **Airtable Setup:** See `docs/airtable-setup.md`
- **Tier Score Formula:** See `docs/scoring-formula.md`
- **Exa MCP Integration:** See `docs/exa-mcp-guide.md`
- **Apollo MCP Integration:** See `docs/apollo-mcp-guide.md`
- **Call Angle Templates:** See `docs/call-angle-templates.md`

---

**You're ready to start working leads. Good luck!**
