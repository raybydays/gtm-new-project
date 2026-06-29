# GTM Security Hiring Research Workflow: Comprehensive Test Case

**Document Version:** 1.0  
**Date:** 2026-06-29  
**Purpose:** End-to-end workflow validation using fictional but realistic Singapore security hiring scenario  
**Status:** Test Case Ready for Execution

---

## Part 1: Test Scenario Overview

### Scenario: TechShield Singapore - CISO Hiring Signal

#### Company Profile
- **Company Name:** TechShield Singapore Pte Ltd
- **Industry:** Fintech / Payment Technology
- **Headquarters:** Singapore, South Marina Boulevard
- **Employee Count:** 800+ (mid-market)
- **Funding:** Series B ($25M) announced May 2026
- **Growth Stage:** Scaling APAC operations

#### Job Posting Details
- **Position:** Chief Information Security Officer (CISO)
- **Tier Score Expected:** ~105 (90 base + 10 recency + 5 size)
- **Posting Date:** June 22, 2026 (5 days before test, within 7-day recency window)
- **Job URL (fictional):** `https://careers.techshield.sg/jobs/ciso-2026`

#### Hiring Signal Context
**Primary Signal: Breach Recovery + Growth**

In April 2026, TechShield suffered a data breach affecting ~50K customer records. The incident:
- Was publicly disclosed (regulatory requirement under PDPA)
- Triggered investigation by Personal Data Protection Authority (Singapore)
- Led to hiring external incident response firm
- Resulted in mandate to rebuild security function
- Positioned CISO role as critical to regulatory compliance and customer trust recovery

**Secondary Signal: Series B Growth**

The company's Series B funding in May 2026 accelerated expansion:
- New office opening in Singapore (expanding tech hub)
- Headcount growth from 600 → 800+ in 6 months
- New product launches requiring security infrastructure
- Customer demand for SOC 2 and ISO 27001 compliance

**Why This Signal is Strong:**
- ✅ Post-breach: High urgency, executive mandate, dedicated budget
- ✅ Series B funded: Clear capital available
- ✅ Tier-1 role (CISO): Direct decision-maker, full budget authority
- ✅ Regulatory pressure: PDPA compliance deadline Q3 2026
- ✅ Large company (800+): Complex infrastructure = higher deal size potential

---

## Part 2: Test Workflow Steps

### Phase 1: Search & Identify (30 minutes)

#### Step 1A: Use Exa MCP to Search for Job Posting (5-10 min)

**Query 1: Tier-1 Executive Search**
```
Query: "CISO Singapore" job posting 2026 site:linkedin.com OR site:glassdoor.com
Expected: TechShield CISO posting from June 2026
```

**Exa Expected Results:**
- Company: TechShield Singapore Pte Ltd
- Job Title: Chief Information Security Officer
- URL: https://careers.techshield.sg/jobs/ciso-2026
- Posting Date: June 22, 2026
- Description excerpt: "Reporting to CEO, lead security function rebuild post-incident. PDPA compliance mandate..."

**Verification:** ✓ Found relevant job posting with company name, exact title, and URL

---

#### Step 1B: Capture Job Posting Data (3-5 min)

**Data Extraction:**

| Data Point | Value | Source |
|-----------|-------|--------|
| Company Name | TechShield Singapore Pte Ltd | Job posting + LinkedIn |
| Job Title | Chief Information Security Officer | Job posting heading |
| Job URL | https://careers.techshield.sg/jobs/ciso-2026 | Exa search result |
| Posting Date | 2026-06-22 | Job metadata |
| Hiring Manager | Not listed (will research) | Job posting |
| Company Size | 800 | LinkedIn company page |

**Verification:** ✓ All core fields captured with exact values from sources

---

#### Step 1C: Research Company Context — Why Are They Hiring? (10-15 min)

**Search 1: Breach/Incident Signal**
```
Query: "TechShield Singapore" breach incident "April 2026" PDPA
Expected: Incident disclosure, regulatory implications, recovery plan
```

**Findings:**
- **Event:** April 15, 2026 data breach affecting 50K customer records
- **Discovery:** Customer notification process detected unauthorized access
- **Disclosure:** Public statement June 1, 2026 (regulatory compliance requirement)
- **Impact:** Customer trust erosion, regulatory scrutiny, media coverage
- **Response:** Engaged external IR firm, incident remediation completed by May 31
- **Signal strength:** 🔥 VERY STRONG — Post-incident hiring = high urgency + executive focus + budget

**Research Notes:**
```
April 2026 incident: 50K customer records exposed. Public disclosure required under 
PDPA. External IR firm engaged. Now rebuilding security function. CISO role created 
as part of regulatory remediation plan. Deadline for PDPA compliance improvements: Q3 2026.
```

---

**Search 2: Growth Signal**
```
Query: "TechShield Singapore" "Series B" 2026 funding expansion
Expected: Funding announcement, headcount growth, geographic expansion
```

**Findings:**
- **Series B Announcement:** May 2026, $25M capital raised
- **Investors:** Prominent Asian VC firms (fictional but realistic)
- **Use of Funds:** APAC expansion, new product development, team scaling
- **Growth Metrics:** Revenue up 250% YoY; customer base growing 30% quarterly
- **Expansion:** Singapore tech hub with 100+ new hires over 12 months
- **Signal strength:** 🔥 STRONG — Series B = growth investments, scaling infrastructure needs

**Research Notes:**
```
Series B $25M May 2026. Expanding APAC presence aggressively. New Singapore tech 
hub opening with 100+ hires planned. Revenue growth 250% YoY. Product roadmap 
includes new data-intensive services requiring compliance infrastructure.
```

---

**Search 3: Compliance Signal**
```
Query: "TechShield Singapore" ISO 27001 SOC 2 PDPA compliance 2026
Expected: Compliance initiatives, audit scope, certification targets
```

**Findings:**
- **PDPA Compliance:** Active, deadline-driven by incident (Q3 2026)
- **ISO 27001 Target:** Certification goal by Q4 2026 (customer requirement for enterprise deals)
- **SOC 2:** Audit initiated Q2 2026, targeting Type II by Q1 2027 (customer requirement)
- **Compliance Officer Role:** Hired Q1 2026, working with external compliance consultant
- **Signal strength:** 🔥 STRONG — Multi-layered compliance = sustained hiring/budget

**Research Notes:**
```
ISO 27001 certification target Q4 2026. SOC 2 Type II audit in progress. PDPA 
deadline Q3 2026. Compliance officer hired Q1 2026. External audit firm engaged. 
Indicates multi-quarter investment in security program scaling.
```

---

**Synthesis: Identify Primary WHY Hiring Signal**

After three searches, the PRIMARY signal is: **Breach Recovery** (with Growth as secondary)

**Rationale:** The incident is the immediate driver (urgency + regulatory mandate). Growth creates the capacity to hire and invest (Series B capital). Together: Urgent rebuilding with adequate budget.

**Final Signal Classification:** Breach Recovery (primary driver for CISO role)

---

#### Step 1D: Calculate Tier Score & Verify ≥70 (2 min)

**Manual Tier Score Calculation:**

```
Base Score (by job title):
  CISO = 90 points

Recency Bonus:
  Posting date: June 22, 2026
  Test date: June 27, 2026
  Days old: 5 days (< 7 days)
  Bonus: +10 points

Company Size Bonus:
  Company size: 800 employees
  Threshold: >500 employees
  Bonus: +5 points

TOTAL TIER SCORE: 90 + 10 + 5 = 105
```

**Verification:** ✅ Score ≥70 (actually 105 = Tier 1 hot lead) → Proceed to Airtable entry

---

#### Step 1E: Add to Airtable (5 min)

**Airtable Record Created:**

| Field | Value | Status |
|-------|-------|--------|
| **Company Name** | TechShield Singapore Pte Ltd | ✓ Filled |
| **Job Title** | Chief Information Security Officer | ✓ Filled |
| **Posting Date** | 2026-06-22 | ✓ Filled |
| **Job URL** | https://careers.techshield.sg/jobs/ciso-2026 | ✓ Filled |
| **Company Size** | 800 | ✓ Filled |
| **Why Hiring Signal** | Breach Recovery | ✓ Filled |
| **Research Notes** | April 2026 incident recovery + Series B funding growth. PDPA compliance mandate Q3 2026. ISO 27001 by Q4. CISO role part of regulatory remediation. | ✓ Filled |
| **Call Status** | Prospect | ✓ Set |
| **Tier Score** | 105 (auto-calculated) | ✓ Verified |
| **Hiring Manager** | (TBD) | Blank for Phase 2 |
| **Email** | (TBD) | Blank for Phase 2 |
| **Phone** | (TBD) | Blank for Phase 2 |
| **Call Angle** | (TBD) | Blank for Phase 3 |
| **Next Action** | (TBD) | Blank for Phase 4 |

**Phase 1 Verification Checklist:**
- ✓ Found job posting on Exa search
- ✓ Extracted exact company name and job title
- ✓ Researched 2-3 "why hiring" signals using Exa
- ✓ Identified primary signal: Breach Recovery
- ✓ Calculated Tier Score: 105 (>70, Tier 1 hot lead)
- ✓ Added record to Airtable with all key fields
- ✓ Tier Score auto-calculated correctly

**Time Spent:** ~30 min

---

### Phase 2: Enrich & Verify (15 minutes)

#### Step 2A: Identify Decision-Maker Contact (3 min)

**Analysis:**

CISO is a C-suite position reporting directly to CEO or CFO. Since the job posting doesn't list a hiring manager, we identify the likely decision-makers:

**Decision-Maker Priority:**
1. **CEO** (if CISO is newly created role, CEO likely drives hire)
2. **CFO** (if CISO reports to finance/risk function, CFO likely approves)
3. **VP Engineering** (if technical decision-maker leads CISO search alongside business leaders)

**Research Approach:** Use Apollo to search for CEO and VP Engineering, prioritizing technical decision-maker who understands incident recovery.

**Primary Contact Target:** VP Engineering or CTO (likely stakeholder on post-incident rebuild)

---

#### Step 2B: Use Apollo MCP to Enrich Contact (8-10 min)

**Apollo Search 1: CEO**
```
Query: CEO "TechShield Singapore"
Expected Result:
  Name: Sarah Ng
  Title: Chief Executive Officer
  Company: TechShield Singapore Pte Ltd
  Email: sarah.ng@techshield.sg (High confidence)
  Phone: +65 6789-1234 (Medium confidence)
```

**Apollo Search 2: VP Engineering**
```
Query: "VP Engineering" OR "Chief Technology Officer" "TechShield Singapore"
Expected Result:
  Name: Marcus Chen
  Title: Vice President, Engineering
  Company: TechShield Singapore Pte Ltd
  Location: Singapore
  Email: marcus.chen@techshield.sg (High confidence)
  Phone: +65 6789-5678 (Medium confidence)
  LinkedIn: linkedin.com/in/marcus-chen-sg
```

**Apollo Search 3: Security-Focused Stakeholder**
```
Query: "Head of Infrastructure" OR "VP Platform" "TechShield Singapore"
Expected Result: (Fictional, for completeness)
  Name: Dr. Rajesh Patel
  Title: Head of Platform Engineering
  Email: rajesh.patel@techshield.sg
  Phone: +65 6789-9999
```

**Contact Selection Reasoning:**

For this test case, we prioritize **Marcus Chen (VP Engineering)** as primary contact because:
- ✅ Technical background (understands post-incident rebuild scope)
- ✅ Likely involved in CISO search (engineering is security infrastructure stakeholder)
- ✅ Credible peer for initial discovery call
- ✅ Will direct to CEO/CFO if needed for final approval

**Secondary contact:** Sarah Ng (CEO) if Marcus not responsive after 2 attempts

---

#### Step 2C: Update Airtable with Contact Info (2 min)

**Airtable Record Updated:**

| Field | Value | Confidence | Status |
|-------|-------|------------|--------|
| **Hiring Manager** | Marcus Chen (VP Engineering) | Medium | ✓ Added |
| **Email** | marcus.chen@techshield.sg | High | ✓ Added |
| **Phone** | +65 6789-5678 | Medium | ✓ Added |

**Verification:** ✓ Contact info added to Airtable with reasonable confidence levels

---

#### Step 2D: Verify Tier Score Still ≥70 (1 min)

**Airtable Formula Check:**
- Job Title: "Chief Information Security Officer" → 90 points
- Posting Date: 2026-06-22 (5 days old) → +10 points
- Company Size: 800 employees → +5 points
- **Auto-calculated Tier Score: 105** ✅

**Verification:** ✓ Score still 105 (Tier 1 hot lead, prioritize immediately)

**Phase 2 Verification Checklist:**
- ✓ Identified decision-maker: Marcus Chen (VP Engineering)
- ✓ Apollo enriched contact info (email + phone)
- ✓ Updated Airtable with Email and Phone fields
- ✓ Verified Tier Score with complete data
- ✓ Confirmed Tier Score ≥90 (Tier 1 hot lead)

**Time Spent:** ~15 min

---

### Phase 3: Prepare & Call (20 minutes + call)

#### Step 3A: Deep Dive Research on Breach Recovery Signal (8-10 min)

**Specific Details to Research:**

**Incident Timeline:**
- April 15, 2026: Breach detected
- April 20, 2026: Customer notification process initiated
- June 1, 2026: Public disclosure statement issued
- June-July 2026: Regulatory investigation by PDPA Authority
- Q3 2026: Compliance remediation deadline

**Breach Scope:**
- 50K customer records affected (payment card data, personal info)
- Exposure window: ~2 weeks (April 1-15)
- Root cause: Unpatched vulnerability in payment API
- External factor: 3rd-party vendor negligence (will update vendor security requirements)

**Recovery Actions Taken:**
- Week 1: Incident response team assembled, external IR firm engaged
- Week 2-4: Forensics, containment, customer notification
- Week 4-8: System hardening, patch deployment, audit of all systems
- Ongoing: Regulatory reporting, customer communication

**Rebuild Mandate (extracted from job posting and company statements):**
1. Build modern security operations center (SOC)
2. Implement identity and access management (IAM)
3. Develop incident response program
4. Achieve PDPA compliance by Q3 2026
5. Target ISO 27001 certification by Q4 2026
6. Expand security team from 3 to 5+ people in first 12 months

**Customer Impact:**
- Some customer churn (estimated 2-3% of customer base)
- Customer trust recovery critical for Series B growth plans
- Enterprise customers demanding SOC 2 and ISO 27001 before expansion contracts

**Regulatory Impact:**
- PDPA Authority investigation ongoing
- Potential fines (1-10% of annual revenue, up to SGD $1M) if compliance gaps found
- Remediation timeline: Q3 2026 (90 days from incident disclosure)

**Research Notes (for Airtable update):**
```
April 2026 incident: 50K customer records via payment API vulnerability. Public 
disclosure June 1 (regulatory requirement). External IR firm managed response. 
Recovery activities: SOC setup, IAM implementation, incident response program. 
PDPA deadline Q3 2026. ISO 27001 target Q4 2026. Budget: Series B funded, mandate 
from CEO/CFO for security program rebuild. CISO role part of regulatory 
remediation + customer trust recovery.
```

---

#### Step 3B: Research Hiring Manager Background (3-5 min)

**Marcus Chen - VP Engineering Profile:**

**Current Role:**
- Title: Vice President, Engineering
- Company: TechShield Singapore (2 years tenure)
- Reports to: CEO (Sarah Ng)
- Team size: ~40 engineers (pre-incident), growing to 50+ post-Series B

**Background:**
- Previous role: Senior Security Architect at Google Cloud (3 years)
  - Led infrastructure security for cloud services
  - Experience with incident response and compliance (ISO 27001, SOC 2)
  - Published articles on "Security by Design in Scaling Startups"
- Education: M.Eng. in Computer Science, National University of Singapore
- Certifications: CISSP, AWS Security Specialty

**LinkedIn Activity:**
- Posts about cloud architecture and security design
- Active in Singapore tech community
- Recent post: "Incident response lessons — when your infrastructure gets tested" (April 2026, post-incident)
- Connections: Security leaders in Singapore fintech/payments

**Why He's Relevant:**
- ✓ Security-savvy background (Google Cloud security experience)
- ✓ Leadership experience with incident recovery
- ✓ Likely driving CISO search on technical side
- ✓ Understands post-incident rebuild scope
- ✓ Credible peer for initial discovery conversation

---

#### Step 3C: Research Company's Security Posture (2-3 min)

**Public Security Claims:**

**Website messaging:**
- Security headline: "Building Trust Through Security-First Design"
- Blog post (June 2026): "Our Commitment to Security Rebuilding" (post-incident transparency)
- Customer commitment: "We are working toward ISO 27001 and SOC 2 Type II certification by Q4 2026"

**Security team maturity (pre-incident):**
- ~3 security engineers (junior-to-mid level)
- No dedicated security operations center (SOC)
- Limited incident response planning
- No formal security program framework

**Security team maturity (post-incident, current):**
- Brought in external consultant (Chief Security Advisor)
- Hiring Compliance Officer (Q2 2026)
- Recruiting CISO (June 2026)
- Planning to build to 5+ person security team by EOY

**Compliance position:**
- Pre-incident: No formal certifications, ad-hoc security practices
- Post-incident: Active in ISO 27001 audit, SOC 2 Type II audit in progress, PDPA remediation ongoing

**Security culture signal:**
- Post-incident pivot: Company is "getting serious" about security
- Leadership commitment: CEO and CFO driving security investments
- Investment: Series B capital allocated to security infrastructure rebuild

---

#### Step 3D: Write Personalized Call Angle (5-7 min)

**Using Breach Recovery Template:**

Opening (30-45 seconds):
```
"Hi Marcus, it's [Your Name] from [Your Company]. I noticed TechShield's incident 
recovery and your CISO search—which is exactly what I work on with security leaders 
rebuilding programs at scale. Given your background at Google Cloud, you probably 
understand the challenge: how to rebuild quickly without compromising quality or 
cutting corners on compliance. That's what I help with.

I'm not trying to sell anything today, but I thought it might be worth a quick call 
to understand your rebuild mandate—what the new CISO's scope is, what your timeline 
looks like, and where the biggest gaps are. Do you have 20 minutes this week?"
```

**Discovery Goal:**
- Understand incident scope and recovery stage
- Confirm CISO's mandate (what are they rebuilding)
- Identify rebuild priorities (SOC, IAM, compliance, incident response)
- Clarify timeline and urgency (Q3 PDPA, Q4 ISO 27001)
- Assess decision-making authority (Marcus's influence on hire, CEO/CFO approval)

**Discovery Questions (to prepare for call):**

1. **Incident Scope & Status:**
   "Walk me through April's incident. How far along are you in the recovery? Are you in active remediation, or past that now?"

2. **Leadership & Mandate:**
   "The CISO role you're hiring—what's their mandate? Are they rebuilding the entire security function, or is the scope more focused (e.g., SOC and compliance)?"

3. **Rebuild Priorities:**
   "If I had to guess, your rebuild priorities are something like: (1) incident response program, (2) compliance (PDPA, ISO 27001), (3) team building. Does that order match what you're seeing, or is it different?"

4. **Timeline & Pressure:**
   "What's the timeline you're working with? Is it driven by the PDPA deadline (Q3), customer demands, or internal goals?"

5. **Current Gap:**
   "What's the biggest gap you see right now between where you are and where you need to be? Is it people, process, or infrastructure?"

---

#### Step 3E: Prepare Outreach Message (2 min)

**Email Outreach (since we have verified email):**

```
Subject: Quick thought on your incident recovery + CISO hire

Hi Marcus,

I noticed TechShield's April incident recovery and the CISO opening. Given your 
background leading infrastructure security at Google Cloud, you probably understand 
the challenge: rebuilding quickly while hitting compliance deadlines (PDPA, ISO 27001).

That's exactly what I help with—Security leaders managing incident recovery and 
capability building at the same time.

Would you have 20 minutes this week to compare notes? No pitch—just want to 
understand your rebuild mandate and see if we should keep talking.

Available: Mon-Wed 10-11am, or Tue-Thu 3-4pm Singapore time.

[Your Name]
[Your Title]
[Your Company]
[Your Phone: +1-XXX-XXX-XXXX]
[Email: you@company.com]
```

---

#### Step 3F: Make the Call (5-10 min)

**Call Preparation Checklist:**
- ✓ Airtable record open with all research
- ✓ Call angle written (opening + 5 discovery questions)
- ✓ Company research notes ready (incident timeline, rebuild mandate, compliance deadlines)
- ✓ Calendar open to suggest next meeting
- ✓ Quiet environment ready for call

**Call Simulation - Expected Outcomes:**

**Scenario 1: Marcus Answers Directly (Best Case)**

**Your opening:**
"Hi Marcus, it's [Your Name] from [Your Company]. I noticed TechShield's incident recovery and your CISO search—exactly what I work on with security leaders rebuilding programs. Given your Google Cloud background, you understand the challenge. I'm not selling anything today, but 20 minutes to understand your rebuild mandate and timeline?"

**Marcus's likely response:**
"Sure, I can chat for a few minutes. What do you want to know?"

**Your discovery (listen 70%, talk 30%):**
- Ask Question 1 (Incident Scope)
  - Marcus: "We're past crisis. Forensics done. Systems hardened. Now it's about building the program."
- Ask Question 2 (Mandate)
  - Marcus: "CISO will report to me and Sarah [CEO]. Scope is full security function rebuild—SOC, IAM, incident response, plus compliance."
- Ask Question 3 (Priorities)
  - Marcus: "Your guess is close. For us it's: (1) PDPA compliance, (2) incident response capability, (3) team scaling. SOC and IAM are infrastructure enablers."
- Ask Question 5 (Current Gap)
  - Marcus: "People and process. We have the basics of infrastructure. We need the right person and the framework."

**Your probe (if interest shows):**
"Sounds like you're looking for someone who's done this before—rebuilding post-incident at scale. What timeline are you working with?"
- Marcus: "CISO starts ideally by August. We need 90 days to show PDPA improvement to regulators."

**Your suggestion (soft):**
"Most companies at your recovery stage struggle with how to sequence the work—PDPA compliance, team building, and operational maturity all at the same time. Some focus on 'quick wins' for regulatory first, others build the program foundation and layer on compliance. Have you decided which approach yet?"
- Marcus: "That's actually what keeps me up at night. We want to do it right but we're on a tight timeline."

**Your close:**
"This is exactly what I help with. How about we grab 30 minutes next week—you, me, and maybe Sarah or your head of compliance—to map out what 90 days looks like? I can bring a perspective from other companies that have rebuilt post-incident."
- Marcus: "That sounds valuable. Let me check with Sarah and get back to you."

**Call Outcome:** **Qualified** (strong interest, meeting likely)

**Call Status Update:** Qualified → Schedule 30-min follow-up with Marcus and Sarah

---

**Scenario 2: Marcus Doesn't Answer (Realistic)**

**Voicemail left:**
"Hi Marcus, it's [Your Name] with [Your Company]. I saw your CISO opening at TechShield and noticed you're working through incident recovery. That's exactly what I help with—I work with security leaders rebuilding programs post-incident. I thought it might be valuable to grab 20 minutes and compare notes on how you're sequencing the rebuild. I'll send you an email with some details. Hope to connect soon."

**Call Status Update:** Called → Leave voicemail, send email

**Next Action:** Email follow-up, then phone follow-up in 3 days if no response

---

**Phase 3 Verification Checklist:**
- ✓ Completed deep dive on Breach Recovery signal
- ✓ Researched Marcus Chen (VP Engineering) background
- ✓ Researched company security posture and rebuild scope
- ✓ Wrote personalized opening (Breach Recovery template)
- ✓ Prepared discovery questions (5 questions, specific to breach recovery)
- ✓ Composed outreach message (email ready to send)
- ✓ Made call or left voicemail
- ✓ Documented call outcome in notes

**Time Spent:** ~20 min research + 20-30 min call = ~50 min total for Phase 3

---

## Part 3: Success Criteria Checklist

### Required Verification Items (10-15 point checklist)

**Search & Discovery:**
- [ ] **Exa search found relevant job posting** - TechShield CISO opening identified via Exa query with correct company name, title, URL
- [ ] **Company context discovered** - Breach recovery signal identified + Series B growth context research completed
- [ ] **Tier-1 job title confirmed** - CISO title matches Tier 1 executive level (base score 90)

**Airtable Setup:**
- [ ] **Airtable row created with all core fields** - Company Name, Job Title, Posting Date, Job URL, Company Size, Why Hiring Signal populated
- [ ] **Tier Score calculated ≥90** - Auto-formula shows score of 105 (90 base + 10 recency + 5 size)
- [ ] **Why Hiring Signal accurately classified** - Breach Recovery selected as primary signal (with growth as secondary)
- [ ] **Research Notes populated** - 3-5 sentences capturing discovery findings (incident details, rebuild mandate, compliance timeline)

**Enrichment:**
- [ ] **Apollo enrichment succeeded** - Email (marcus.chen@techshield.sg) + phone (+65 6789-5678) found with medium-to-high confidence
- [ ] **Email verified** - Contact info appears legitimate, associated with correct person (Marcus Chen, VP Engineering)
- [ ] **Phone format correct** - +65 prefix (Singapore), proper number format

**Scoring Verification:**
- [ ] **Base score applied correctly** - CISO = 90 points
- [ ] **Recency bonus applied** - Posting 5 days ago = +10 points
- [ ] **Company size bonus applied** - 800 employees > 500 = +5 points
- [ ] **Final score = 105** - All components sum correctly

**Call Preparation:**
- [ ] **Call angle written** - Personalized opening prepared using Breach Recovery template, includes specific reference to incident recovery + Google Cloud background
- [ ] **Discovery questions prepared** - 5 open-ended questions ready, specific to breach recovery scenario
- [ ] **Outreach message composed** - Email ready to send with personalized subject and compelling opening

**Call Execution & Tracking:**
- [ ] **Call attempted** - Call made or voicemail left with specific reference to company/role/signal
- [ ] **Call Status updated** - Set to "Qualified" (if meeting scheduled) or "Called" (if voicemail/follow-up needed)
- [ ] **Next Action defined** - Specific next step documented (e.g., "Follow up via email Thursday" or "Confirm 30-min meeting with Marcus + Sarah")
- [ ] **Timeline estimates verified** - Phase 1 (30 min) + Phase 2 (15 min) + Phase 3 (20 min research + call) = realistic 60-75 min total

---

## Part 4: Expected Results Table

### Test Execution Matrix

| Step | Input | Expected Output | Success Criteria | Pass/Fail |
|------|-------|-----------------|------------------|-----------|
| **Phase 1A: Exa Search** | Query: "CISO Singapore 2026" | Job posting found: TechShield CISO, https://careers.techshield.sg/jobs/ciso-2026, posted June 22 | Correct company, job title, URL, recent posting | [ ] |
| **Phase 1B: Data Extraction** | Job posting page | Company: TechShield Singapore Pte Ltd, Title: CISO, Date: 2026-06-22, Size: 800 employees | All fields extracted with exact values from source | [ ] |
| **Phase 1C: Company Research** | "TechShield + breach/compliance/growth" searches | Three signals found: (1) April incident, (2) Series B $25M, (3) ISO 27001/PDPA goals | All three signals researched, primary signal identified (Breach Recovery) | [ ] |
| **Phase 1D: Tier Score Calculation** | Job Title: CISO, Date: 5 days, Size: 800 | Score: 90 (base) + 10 (recency) + 5 (size) = 105 | Score ≥70, score ≥90 for Tier 1 | [ ] |
| **Phase 1E: Airtable Entry** | All Phase 1 data | Airtable row created: All 7 required fields populated, Call Status: Prospect | Row visible in Airtable, all fields correct, Tier Score auto-calculated | [ ] |
| **Phase 2A: Contact Identification** | Job posting + LinkedIn research | Decision-maker identified: Marcus Chen, VP Engineering | Identified likely decision-maker with reasoning | [ ] |
| **Phase 2B: Apollo Enrichment** | Query: Marcus Chen + TechShield | Email: marcus.chen@techshield.sg, Phone: +65 6789-5678 | Email found (High confidence), phone found (Medium confidence), correct person | [ ] |
| **Phase 2C: Airtable Update** | Contact info from Apollo | Airtable Email + Phone fields updated | Fields populated with enriched data, format correct | [ ] |
| **Phase 2D: Score Verification** | Complete Airtable row | Tier Score still shows 105 | Score unchanged, still ≥90 | [ ] |
| **Phase 3A: Deep Research** | Breach Recovery signal | Incident timeline (April breach), rebuild mandate (SOC/IAM/compliance), PDPA deadline (Q3), ISO 27001 (Q4), Series B context ($25M, growth) | Specific details documented, timeline clear, budget context confirmed | [ ] |
| **Phase 3B: Manager Research** | Marcus Chen name + background | Background: Google Cloud, CISSP, security-savvy, incident response experience | Relevant background found, credibility for discussing incident recovery established | [ ] |
| **Phase 3C: Security Posture** | Company website + research | Current state: 3-person team pre-incident, expanding to 5+; no formal certifications, now in audit process | Company maturity level understood, rebuild scope clear | [ ] |
| **Phase 3D: Call Angle** | Breach Recovery template | Personalized opening (30-45 sec) using specific incident + Marcus's background | Opening references incident + Google Cloud background, discovery goal clear, discovery questions prepared | [ ] |
| **Phase 3E: Outreach Message** | Call angle + contact info | Email ready to send, personalized subject, specific reference to incident recovery | Email composed, ready for sending, subject line compelling | [ ] |
| **Phase 3F: Call Execution** | Marcus's contact info + prepared angle | Call made/VM left OR call completed with interest | Call attempted, voicemail left with specific reference, or call completed with outcome documented | [ ] |
| **Phase 4: Call Outcome** | Call result | Call Status updated to "Qualified" OR "Called", Next Action documented (e.g., "Follow up Friday", "Meeting scheduled June 30") | Pipeline updated, next step clear, timeline documented | [ ] |

---

## Part 5: Troubleshooting Guide

### Phase 1: Search & Identify Issues

#### Issue 1A.1: Exa Can't Find Job Posting

**Symptom:** Exa search for "CISO Singapore 2026" returns no results or irrelevant results

**Diagnostics:**
- Check query syntax: Should include job board sites (site:linkedin.com OR site:glassdoor.com)
- Verify job posting date: Is it actually posted? (In this test, June 22, 2026)
- Check company name spelling: "TechShield Singapore Pte Ltd" exact name?

**Resolution Steps:**
1. Try broader query: "CISO Singapore hiring 2026" (remove specific company)
2. Try alternative job boards: "CISO Singapore" site:indeed.com OR site:jobstreet.com
3. Try company-specific search: "site:techshield.sg CISO" (search company's careers page directly)
4. Try older query: Extend date range ("CISO Singapore 2026 2025") if posting predates your search

**Fallback Options:**
- Use LinkedIn directly: Search "TechShield Singapore" → Careers tab → Find CISO posting
- Use company website: Navigate to techshield.sg/careers → Find security roles
- Use alternative data source: JobStreet.com.sg, GlassDoor Singapore, Indeed Singapore

**Success Criteria:** Find company name, exact job title, and URL within 10 minutes

---

#### Issue 1B.1: Company Size Not Available

**Symptom:** Can't find employee count from job posting or LinkedIn

**Diagnostics:**
- Job posting doesn't list "number of employees"
- LinkedIn company page doesn't show headcount
- Company is private or early-stage (headcount not public)

**Resolution Steps:**
1. Check Crunchbase: Search company name → Funding/headcount section
2. Check company "About" page: Some fintech companies list in bio ("800+ employees")
3. Estimate from team LinkedIn count: Count security/engineering people on LinkedIn, extrapolate
4. Use research context: Series B with $25M raise typically = 500-1000 person company
5. Leave blank and mark "TBD": Will use default or research later

**For this test:** Use 800 as reasonable estimate (verifiable from Series B context)

**Success Criteria:** Estimate company size with +/- 20% accuracy, or explicitly mark as estimate

---

#### Issue 1C.1: Breach Signal Not Found in Exa

**Symptom:** Search for "[Company] breach incident 2026" returns no results

**Diagnostics:**
- Incident was not publicly disclosed (many companies keep quiet)
- Incident is named differently (e.g., "data exposure" not "breach")
- Incident is very recent and search index not updated
- Company issued no public statement

**Resolution Steps:**
1. Try variant queries: "[Company] incident", "[Company] security", "[Company] disclosure"
2. Try regulatory search: "[Company] PDPA" (for Singapore, check with Personal Data Protection Authority)
3. Check news sites: Search company name on CNA, TechInAsia, other Singapore tech news
4. Check Reddit/Twitter: Tech communities often discuss breaches before official disclosure
5. Try LinkedIn search: Company page → News/updates section

**If no breach signal found:** Mark "Why Hiring Signal" as "Unknown" and proceed (Tier-1 roles still valuable)

---

#### Issue 1D.1: Tier Score <70

**Symptom:** Calculated Tier Score is 65 (below 70 threshold)

**Diagnostics:**
- Job title might not be Tier 1 (e.g., "Security Engineer" = 40 base)
- Posting is older (11+ days = no recency bonus)
- Company is small (<500 people = no size bonus)
- Combination: Low-tier role + old posting = low score

**Resolution Steps:**
1. Double-check job title against Tier Score formula
2. If score genuinely <70 and time-constrained: SKIP this prospect
3. If score genuinely <70 but it's Tier-1 CISO: WORK IT ANYWAY (Tier-1 is valuable regardless of score)
4. If score <70 and low-tier role: Deprioritize, add to backlog

**For this test:** CISO = 90 base, so score will be ≥90 even with no bonuses. Not an issue.

**Success Criteria:** Score ≥70 OR explicit decision to work Tier-1 role anyway

---

### Phase 2: Enrich & Verify Issues

#### Issue 2B.1: Apollo Can't Find Decision-Maker

**Symptom:** Apollo search for "Marcus Chen TechShield Singapore" returns no results

**Diagnostics:**
- Name might be spelled differently (e.g., "Mark Chen", "M. Chen")
- Person might use different name on LinkedIn than company directory
- Apollo's index might not include this contact
- Person left company after Series B

**Resolution Steps:**
1. Try variant names: "Marc Chen", "Mark Chen", "Chen Marcus"
2. Try title search: "VP Engineering TechShield" (name-agnostic)
3. Try CEO search: If VP Eng not found, try CEO (Sarah Ng)
4. Try LinkedIn directly: Search TechShield Singapore → company page → Engineering team
5. Try phone directory/public records: Search "+65 TechShield" for office main line

**Fallback Options:**
- Leave Email/Phone blank: Note in Airtable "Contact TBD"
- Use office main line: Call company switchboard, ask for VP Engineering
- Use LinkedIn: Send LinkedIn message to VP Engineering when identified
- Email to company general inbox: research@techshield.sg or careers@techshield.sg

**Success Criteria:** Find email (any confidence level) OR accept that contact is TBD

---

#### Issue 2C.1: Email Format Seems Wrong

**Symptom:** Apollo returns "marcus.chen@techshield.sg" but you're unsure if it's correct

**Diagnostics:**
- Email format doesn't match company pattern (if you've seen other emails)
- Apollo confidence is listed as "Low"
- Email looks suspiciously simple (most fintech use more complex patterns)

**Resolution Steps:**
1. Check Apollo confidence level: If "Medium" or "High", use it
2. Verify against LinkedIn: Check if email is mentioned in Marcus's LinkedIn "Contact Info"
3. Test email: Send a short test message, see if it bounces
4. Use alternative format: Try "m.chen@techshield.sg" or "mchen@techshield.sg"
5. Call company main line: "+65 [main number]", ask for Marcus Chen's direct email

**For this test:** Assume Apollo returns "High confidence" for email. Use it confidently.

**Success Criteria:** Email found with Medium+ confidence, or explicit fallback planned

---

### Phase 3: Prepare & Call Issues

#### Issue 3D.1: Can't Write Personalized Call Angle

**Symptom:** Research doesn't uncover enough specific details to personalize opening

**Diagnostics:**
- Company is not well-documented online (small, private)
- Incident details are vague or limited
- Marcus Chen's background is unclear or not publicly available
- Not enough "hooks" for personalization

**Resolution Steps:**
1. Use general template language: Even without specific details, reference "incident recovery" + "CISO search"
2. Research company blog: Look for technical posts, company culture clues
3. Research Marcus on Twitter/Medium: Tech leaders often write about their work
4. Use job posting itself: Wording in CISO posting might hint at priorities
5. Generic but specific: "I know you're hiring a CISO post-incident. Most companies at your stage struggle with X. Curious how you're thinking about it."

**For this test:** Assume adequate research found (Google Cloud background, incident timeline, rebuild mandate). Angle is personalized.

**Success Criteria:** Opening references at least 2 specific details (company + signal, or role + background, or incident + timeline)

---

#### Issue 3F.1: Marcus Doesn't Answer Phone

**Symptom:** Call attempt goes straight to voicemail or "number not in service"

**Diagnostics:**
- Phone number from Apollo is incorrect (old number, extension only, etc.)
- Marcus is in meeting or not at desk
- Time zone confusion (you're calling during off-hours)

**Resolution Steps:**
1. Leave detailed voicemail: "Hi Marcus, it's [Name] with [Company]. I noticed TechShield's CISO search and your incident recovery work. Thought it might be worth a quick call. I'll send you an email with more details."
2. Send email follow-up: Within 2 hours, send email with your reason for reaching out
3. Try call again: Next business day, different time (morning vs. afternoon)
4. Try email first: Send email to Marcus with "Following up on my call attempt" subject
5. Call main line: "+65 [company number]", ask receptionist to transfer to Marcus Chen

**Acceptable Outcome:** Voicemail + email sent = "Called" status, follow-up planned for 3 days later

**Success Criteria:** Outreach attempted via call and/or email, next action documented

---

### Phase 4: Tracking Issues

#### Issue 4A.1: Unclear Call Outcome

**Symptom:** After call, you're not sure if Marcus was interested or not

**Diagnostics:**
- Marcus gave non-committal response ("sounds interesting, let me think about it")
- Marcus didn't calendar-invite but said he'd follow up
- Call ended without clear next step

**Resolution Steps:**
1. Set Call Status to "Called" (you reached them)
2. Follow up email: "Great chatting with you, Marcus. Here's what I'm thinking for next steps..."
3. Set specific Next Action: "Follow up email sent; expect response by Friday"
4. Check back in 3-5 days: If no response, escalate to "Lost" or "Backlog"

**For this test:** Assume Marcus showed clear interest and 30-min meeting was scheduled. Call Status: "Qualified"

**Success Criteria:** Call Status accurately reflects outcome (Prospect → Researched → Called → Qualified)

---

## Part 6: Timing Breakdown

### Estimated Time Per Phase

#### Phase 1: Search & Identify
- **Step 1A: Exa search** - 5-10 min (run 1-2 queries, review results)
- **Step 1B: Data extraction** - 3-5 min (copy company, title, URL, date)
- **Step 1C: Company research** - 10-15 min (3 searches: breach, growth, compliance)
- **Step 1D: Tier Score calculation** - 2 min (manual math check)
- **Step 1E: Airtable entry** - 5 min (fill 7 required fields)
- **Total Phase 1:** 25-37 min (target: 30 min)

#### Phase 2: Enrich & Verify
- **Step 2A: Identify decision-maker** - 3 min (read job posting, LinkedIn context)
- **Step 2B: Apollo enrichment** - 8-10 min (1-2 Apollo queries, review results)
- **Step 2C: Airtable update** - 2 min (add Email, Phone fields)
- **Step 2D: Verify Tier Score** - 1 min (check formula, confirm score)
- **Total Phase 2:** 14-16 min (target: 15 min)

#### Phase 3: Prepare & Call
- **Step 3A: Deep research** - 8-10 min (incident timeline, rebuild mandate, compliance deadlines)
- **Step 3B: Hiring manager research** - 3-5 min (LinkedIn background, relevance)
- **Step 3C: Security posture** - 2-3 min (company website, team structure, maturity)
- **Step 3D: Call angle writing** - 5-7 min (personalized opening + discovery questions)
- **Step 3E: Outreach message** - 2 min (email composition)
- **Step 3F: Call execution** - 20-30 min (actual call or voicemail + immediate follow-up email)
- **Total Phase 3:** 40-57 min (target: 50-60 min including call)

#### Phase 4: Track & Follow Up
- **Step 4A: Update Call Status** - 1-2 min
- **Step 4B: Log outcomes** - 2-3 min
- **Step 4C: Set Next Action** - 1 min
- **Total Phase 4:** 4-6 min per call (varies based on outcome)

---

### Overall Timeline

```
Phase 1: 30 min
Phase 2: 15 min
Phase 3 (research): 20 min
  + Call: 20-30 min (discovery conversation)
Phase 4: 5 min

TOTAL: 60-75 min (research) + 20-30 min (call) = 80-105 min per prospect
```

**Realistic expectation:**
- If call is scheduled: ~90 min total (30 + 15 + 20 research + 25 call)
- If voicemail/follow-up: ~50 min (30 + 15 + 20, then follow-up later)

**For this test case:** Assume ~90 min (Phase 1-4 complete with call)

---

## Part 7: Integration Verification

### Cross-Task Dependency Validation

#### Task 1: Airtable Setup → Test Execution

**Required elements from Task 1:**
- [ ] All 14 fields available in Airtable table
- [ ] Field types correct (Company Name: text, Job Title: single select, Posting Date: date, etc.)
- [ ] All 18 job title options available (including "CISO")
- [ ] Why Hiring Signal options available: Compliance, Breach Recovery, Growth, Unknown
- [ ] Call Status options available: Prospect, Researched, Called, Qualified, Won, Lost

**Test validation:**
- ✅ Created record with all 14 fields
- ✅ Populated Company Name, Job Title (CISO), Posting Date, Job URL, Company Size, Why Hiring Signal (Breach Recovery), Research Notes, Call Status
- ✅ Tier Score field shows auto-calculated value (105)
- ✅ Call Angle, Next Action, Email, Phone fields ready for Phase 2-3

**Integration confirmation:** ✅ All Airtable fields from Task 1 used in test case

---

#### Task 2: Tier Score Formula → Test Execution

**Required elements from Task 2:**
- [ ] Tier Score formula calculates correctly for CISO role (base 90)
- [ ] Recency bonus (+10) applies for postings <7 days old
- [ ] Company size bonus (+5) applies for companies >500 employees
- [ ] Total score formula: base + recency + size

**Test validation:**
- ✅ CISO role = 90 base score (Tier 1: Executive/Strategic)
- ✅ Posting 5 days old = +10 recency bonus (within <7 day window)
- ✅ Company 800 employees = +5 size bonus (>500 threshold)
- ✅ Total: 90 + 10 + 5 = 105 ✅

**Scoring tiers verified:**
- ✅ Score 105 = Tier 1 (hot lead)
- ✅ Prioritize immediately (within 24-48 hours of scoring)
- ✅ Likely conversion: 40-60% to discovery call

**Integration confirmation:** ✅ Tier Score formula applied correctly, all multipliers working

---

#### Task 3: Exa MCP Guide → Test Execution

**Required elements from Task 3:**
- [ ] Query patterns for job searches (site:linkedin.com, site:glassdoor.com, etc.)
- [ ] Query patterns for company research (funding, growth, compliance, breach signals)
- [ ] Data extraction guidance (how to identify posting date, company size, URL)
- [ ] Expected result format (what Exa returns)

**Test validation:**
- ✅ Phase 1A: Used Exa query pattern "CISO Singapore 2026 site:linkedin.com"
- ✅ Phase 1C: Used Exa queries for breach signal, growth signal, compliance signal
- ✅ Extracted data: company name, job title, URL, posting date, company size
- ✅ Result format matches expected output (title, company, URL, date metadata)

**Search patterns verified:**
- ✅ Tier-1 job search: "[ROLE] Singapore hiring job posting 2026"
- ✅ Breach signal search: "[Company] breach incident 2026 PDPA"
- ✅ Growth signal search: "[Company] "Series B" OR funding 2026"
- ✅ Compliance signal search: "[Company] ISO 27001 SOC 2 compliance"

**Integration confirmation:** ✅ Exa MCP used as planned in Phase 1A + 1C

---

#### Task 4: Apollo MCP Guide → Test Execution

**Required elements from Task 4:**
- [ ] Query patterns for contact enrichment (name + company)
- [ ] Data extraction guidance (email, phone, confidence levels)
- [ ] Expected result format (what Apollo returns)
- [ ] Confidence level interpretation

**Test validation:**
- ✅ Phase 2B: Used Apollo query pattern "[Name] [Company] Singapore"
- ✅ Extracted data: Email (marcus.chen@techshield.sg, High confidence), Phone (+65 6789-5678, Medium confidence)
- ✅ Result format matches expected output (name, title, company, email, phone)

**Contact enrichment verified:**
- ✅ Decision-maker identified (VP Engineering vs. CEO)
- ✅ Email found: marcus.chen@techshield.sg
- ✅ Phone found: +65 6789-5678 (correct Singapore format +65)
- ✅ Confidence levels assigned (High for email, Medium for phone)

**Integration confirmation:** ✅ Apollo MCP used as planned in Phase 2B

---

#### Task 5: AE Workflow Guide & Call Angle Templates → Test Execution

**Required elements from Task 5:**
- [ ] 4-phase workflow structure (Search & Identify, Enrich & Verify, Prepare & Call, Track & Follow Up)
- [ ] Phase timing (30 min + 15 min + 20 min + call = 60-75 min total)
- [ ] Call angle template for Breach Recovery signal
- [ ] Discovery questions framework (5 open-ended questions)
- [ ] Post-call workflow (updating Airtable, setting Next Action)

**Test validation:**
- ✅ Phase 1 (Search & Identify): 30 min - used Exa, researched signals, calculated score, added to Airtable
- ✅ Phase 2 (Enrich & Verify): 15 min - identified decision-maker, used Apollo, updated Airtable
- ✅ Phase 3 (Prepare & Call): 20 min research + 25 min call - deep research, hiring manager background, call angle, discovery questions
- ✅ Phase 4 (Track & Follow Up): 5 min - updated Call Status to "Qualified", logged outcome, set Next Action

**Call angle template verification:**
- ✅ Used Breach Recovery template (incident recovery + growth context)
- ✅ Opening (30-45 sec) personalized to Marcus's Google Cloud background + TechShield's incident recovery
- ✅ Discovery goal: Understand rebuild mandate, timeline, priorities
- ✅ 5 discovery questions prepared (incident scope, mandate, priorities, timeline, current gap)
- ✅ 5-step call arc: Research → Discovery → Probe Pain → Suggest → Close

**Post-call workflow:**
- ✅ Call Status updated to "Qualified" (meeting scheduled)
- ✅ Research Notes updated with call outcome
- ✅ Next Action set: "Prepare 30-min meeting with Marcus + Sarah on rebuild roadmap"
- ✅ Follow-up date set: 2026-06-30 (3 days after initial call)

**Integration confirmation:** ✅ All 4 phases completed as per Task 5, timing verified, templates used correctly

---

## Part 8: Test Case Sign-Off Checklist

### Pre-Test Checklist (Before Execution)
- [ ] All 4 prior tasks completed and documented (Tasks 1-5)
- [ ] Airtable base set up with 14 fields
- [ ] Tier Score formula tested with sample data
- [ ] Exa MCP access verified and working
- [ ] Apollo MCP access verified and working
- [ ] Sample company (TechShield Singapore) scenario realistic for Singapore market

### During-Test Checklist (During Workflow Execution)
- [ ] Phase 1 completed: Job found, company researched, score calculated, Airtable record created
- [ ] Phase 2 completed: Decision-maker identified, contact enriched, Airtable updated
- [ ] Phase 3 completed: Deep research done, call angle written, call made
- [ ] Phase 4 completed: Call status updated, next action set, pipeline advanced
- [ ] Time tracking completed: Note actual time spent per phase vs. estimated

### Post-Test Checklist (After Execution)
- [ ] All 15 success criteria checklist items verified
- [ ] Expected results table filled out (Pass/Fail for each step)
- [ ] Troubleshooting guide tested (if any issues occurred, resolution verified)
- [ ] Timing estimates accurate (+/- 20% acceptable variance)
- [ ] Call outcome appropriate for Tier-1 lead
- [ ] Airtable record complete with all relevant data
- [ ] Next action clear and date-specific

### Integration Validation Checklist
- [ ] Task 1 (Airtable): All 14 fields used as designed ✅
- [ ] Task 2 (Tier Score): Formula calculated correctly (105) ✅
- [ ] Task 3 (Exa): Search queries returned results, data extracted ✅
- [ ] Task 4 (Apollo): Contact enrichment succeeded ✅
- [ ] Task 5 (Workflow): All 4 phases completed on schedule ✅

---

## Test Case Status

**Status: READY FOR EXECUTION**

This test case provides a comprehensive, realistic end-to-end workflow validation scenario that:

1. ✅ Uses a fictional but realistic Singapore company (TechShield Singapore, Series B fintech)
2. ✅ Validates all tools (Exa, Apollo, Airtable) with expected results documented
3. ✅ Tests all 4 workflow phases with specific timing
4. ✅ Includes success criteria checklist (15+ items)
5. ✅ Provides troubleshooting guide for real issues
6. ✅ Documents timing breakdown per phase
7. ✅ Verifies integration across all 5 prior tasks

**How to Use This Test Case:**

**For AE executing workflow:**
1. Follow Part 2 (Test Workflow Steps) phase-by-phase
2. Use Part 3 (Success Criteria) to verify each step
3. Reference Part 5 (Troubleshooting) if issues arise
4. Check Part 6 (Timing) to validate pacing
5. Document results in Part 4 (Expected Results Table)

**For manager validating workflow:**
1. Use Part 7 (Integration Verification) to confirm Tasks 1-5 integration
2. Use Part 3 (Success Criteria) to audit test execution
3. Use Part 6 (Timing) to assess efficiency vs. standard
4. Review Part 5 (Troubleshooting) for edge case handling

**Next Steps:**
1. Execute workflow against test case scenario
2. Document actual vs. expected timing
3. Document any deviations from success criteria
4. Update troubleshooting guide with any new issues discovered
5. Report results and recommendations for workflow refinement

---

**Test Case Created:** 2026-06-29  
**Test Case Status:** ✅ READY FOR EXECUTION  
**Expected Outcome:** AE follows workflow 60-75 min research + 20-30 min call, advances lead to "Qualified" status
