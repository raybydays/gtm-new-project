# GTM Security Hiring Workflow: AE Quick Reference Sheet

**Print this page and keep it at your desk while working leads.**

---

## The 4-Phase Workflow (60-75 min per prospect)

```
PHASE 1: Search & Identify (30 min)     PHASE 2: Enrich & Verify (15 min)
├─ Find job posting (Exa)               ├─ Identify decision-maker
├─ Extract company info                 ├─ Apollo: Get email + phone
├─ Research Why Hiring Signal           ├─ Update Airtable
└─ Add to Airtable + Tier Score         └─ Verify Tier Score ≥70

PHASE 3: Prepare & Call (20 min + call)  PHASE 4: Track & Follow Up (5 min)
├─ Deep research on signal              ├─ Update Call Status
├─ Research hiring manager              ├─ Log outcome in Research Notes
├─ Research company security posture    ├─ Set Next Action (specific date)
├─ Write personalized call angle        └─ Schedule follow-up
├─ Prepare outreach message
└─ Make call (20-30 min)
```

---

## Tier Score Quick Reference

| Tier | Score Range | Job Title | Priority | When |
|------|-------------|-----------|----------|------|
| **1** | 90-105 | CISO, VP Security, Head of Security | 🔥 Hot | This week |
| **2** | 70-89 | Director, Manager, Architect | ⭐ Good | Next 2 weeks |
| **3** | 60-79 | Senior Engineer, Compliance Lead | 💼 Backlog | If slow |
| **4** | 40-59 | Engineer, Analyst | 📋 Skip | Low priority |

**Quick Scoring:**
```
Base Score:    CISO/VP = 90 | Director = 75 | Architect = 60 | Engineer = 40
Recency +10:   Posted 0-6 days ago? Yes = +10
Company +5:    >500 employees? Yes = +5
TOTAL:         Base + Recency + Size
```

**Decision Rule:** Score ≥70? Add to Airtable. Score <70 AND low tier? Skip.

---

## Exa MCP: Query Cheat Sheet

**Tier-1 Job Search:**
```
CISO Singapore hiring 2026 site:linkedin.com OR site:glassdoor.com
"VP Security" OR "VP Information Security" Singapore job 2026
```

**Why Hiring Signal Searches:**

**Growth:** `[Company] funding Series A OR Series B OR expansion 2026`

**Compliance:** `[Company] PDPA OR ISO 27001 OR SOC 2 compliance 2026`

**Breach:** `[Company] breach OR incident OR security alert 2026`

---

## Apollo MCP: Contact Enrichment

**Query Format:**
```
[First Name] [Last Name] [Company Name] Singapore
OR
[Job Title] [Company Name] Singapore
```

**Example:** `Marcus Chen TechShield Singapore` or `VP Engineering TechShield`

**What Apollo Returns:**
- Name + Title + Email (with confidence: High/Medium/Low)
- Phone (with confidence level)
- LinkedIn profile

**If no result:** Try variant names (Marc vs. Mark), try company CEO, try job title instead of name.

---

## Airtable: 14 Fields to Fill

| Phase | Required Fields | Optional Fields |
|-------|-----------------|-----------------|
| **Phase 1** | Company Name, Job Title, Posting Date, Job URL, Company Size, Why Hiring Signal, Call Status | Research Notes |
| **Phase 2** | Email, Phone | Hiring Manager |
| **Phase 3** | Call Angle | Next Action |
| **Phase 4** | (Update) Call Status | Research Notes, Next Action |

**Critical:** Copy-paste exact job title and company name (don't paraphrase).

---

## Why Hiring Signal: Pick ONE Primary Signal

| Signal | Indicators | Your Angle | Timeline |
|--------|-----------|-----------|----------|
| **Growth** | Series A/B, expansion, new market, new product, headcount growth | "As you scale, security infrastructure lag = risk" | Medium urgency |
| **Compliance** | PDPA, ISO 27001, SOC 2, audit requirements | "Compliance deadline = real pressure + budget" | High urgency |
| **Breach** | Incident disclosure, post-incident hiring, recovery signal | "Rebuild fast without cutting corners" | VERY URGENT |
| **Unknown** | No clear signal found after 10-15 min research | "Curious about what's driving this hire" | Exploratory |

**Rule:** If you find both Growth + Compliance, pick Growth (growth is primary driver).

---

## Call Angle Templates (30-45 sec opening)

### Template: Growth Signal
> "Hi [Name], I noticed [Company] closed your Series B / announced [expansion]. That kind of growth puts pressure on your security infrastructure. I help security leaders close that gap as you scale. Not selling anything today—just want to understand your mandate and see if we should talk more. 20 minutes this week?"

### Template: Compliance Signal
> "Hi [Name], I saw [Company] is targeting [ISO 27001/SOC 2/PDPA compliance]. I work with security teams navigating compliance deadlines without reinventing the wheel. Curious about your timeline and what the gap is right now. 20 minutes this week?"

### Template: Breach Recovery
> "Hi [Name], I know you're working through incident recovery. That's exactly what I help with—rebuilding quickly without cutting corners. Given your [Google Cloud/relevant background], you understand the challenge. 20 minutes to understand your rebuild mandate?"

### Template: Unknown Signal
> "Hi [Name], CISO roles are rare. Curious what's driving this hire right now? I work with security leaders through transitions like this. Would be worth 20 minutes to understand your situation."

---

## Discovery Questions: Pick 3-5 Most Relevant

### Growth Signal:
1. "Walk me through the growth—what's driving it most? New markets, new products, or scaling existing?"
2. "What's the mandate for the CISO/security leader you're hiring? Building from scratch or scaling?"
3. "What's the biggest gap right now—people, process, tools, or strategy?"

### Compliance Signal:
1. "What's the compliance requirement and timeline? PDPA? ISO? When's the deadline?"
2. "Where are you today? Starting from scratch or partial foundation?"
3. "What's the gap—people, process, or tools?"

### Breach Recovery:
1. "Walk me through the incident. How far along are you in recovery?"
2. "What's the new CISO's mandate? Full function rebuild or focused area?"
3. "What's your biggest pain point right now?"

---

## Call Execution Checklist

**Before you dial:**
- [ ] Airtable open with research
- [ ] Call angle written (30-45 sec opening)
- [ ] 3-5 discovery questions visible
- [ ] Company research notes ready (signal details, timeline, budget)
- [ ] Calendar open (for scheduling follow-up)

**During the call:**
- [ ] Listen 70%, talk 30%
- [ ] Ask, don't tell
- [ ] Take notes
- [ ] Find the pain point
- [ ] If interested: "Should we schedule 30 minutes next week to dig deeper?"

**If voicemail:**
- [ ] Leave specific reference to company + signal (e.g., "I noticed your CISO search and incident recovery")
- [ ] Keep to 20-30 seconds
- [ ] Mention you're sending an email

**If wrong person:**
- [ ] Ask who the right contact is
- [ ] Note name/email in Research Notes
- [ ] Say you'll follow up with them

---

## Call Outcomes: Update Airtable

| Outcome | Call Status | Next Action | Follow-Up |
|---------|------------|-------------|-----------|
| Reached, interested | **Qualified** | "Schedule 30-min with [Name] on [date]" | Confirm meeting |
| Reached, curious | **Called** | "Follow up Friday; send case study" | +3 days |
| Voicemail/no answer | **Called** | "Call back Thursday; try email Wed" | +3 days |
| Wrong person | **Called** | "Follow up with [new contact name]" | +3 days |
| Not interested | **Lost** | "Mark as lost; note reason" | Quarterly revisit |

---

## Time Budget

**For 1 prospect (Tier 1 lead):**

| Phase | Time | Buffer | Total |
|-------|------|--------|-------|
| Phase 1: Search & ID | 30 min | +5 min | 35 min |
| Phase 2: Enrich | 15 min | +3 min | 18 min |
| Phase 3: Prep | 20 min | +5 min | 25 min |
| Call | 20-30 min | +10 min | 30-40 min |
| **Total** | **85-95 min** | — | **1.5 hours per lead** |

**Realistic daily:** 1-2 leads per 4-5 hours = 2-3 Qualified leads per week

---

## Troubleshooting Quick Fixes

| Problem | Quick Fix |
|---------|-----------|
| **Exa finds no results** | Try broader query, try company careers page directly, try LinkedIn search |
| **Apollo finds no email** | Try variant names, try CEO instead, try office main line, email company general inbox |
| **Score <70** | If Tier-1 role (CISO/VP), work it anyway. If Tier 3-4, skip if time-short |
| **Tier Score formula broken** | Check field names match exactly (case-sensitive), check field types (Single Select for Job Title, Date for Posting Date, Number for Company Size) |
| **Can't reach prospect** | Leave VM, send email, try phone again 3 days later, check for new contact info |
| **Wrong person answers** | "Can you direct me to [Title]? I'll follow up with them directly." Ask for email/phone. |

---

## Weekly Pipeline Check (Friday)

**Sort Airtable by Call Status:**

1. **Qualified** (scheduled meetings)
   - How many? (Target: 2-3)
   - Are discovery calls prepped?

2. **Called** (waiting for response)
   - Any overdue for follow-up?
   - Any stuck >2 weeks?

3. **Prospect** (not yet contacted)
   - Any Tier 1 (90+) not worked?
   - Any dropped by mistake?

4. **Lost** (explicitly rejected)
   - Any that might be "revisit later"?

**Action:** If <2 Qualified, need more Phase 1 searches. If many Called/no response, adjust angle or move to Lost.

---

## Singapore Job Market Context

**Tier-1 Rarity:** CISO/VP Security roles in Singapore are **rare**. When you find one:
- Tier Score ≥90? Work it immediately
- Don't wait for "perfect time" to call
- Expect competition (other recruiters, internal hiring)

**Compliance Pressure:** Singapore enforces PDPA strictly
- Most fintech/healthtech companies running compliance projects
- "Compliance signal" is credible and common
- Deadlines are real (regulators follow through)

**Series B Market:** Singapore Series B companies are scaling fast
- Growth signal is credible
- Budget is real (not always, but often)
- CEO/VP buy-in for security is increasing (especially post-incident)

**Post-Incident Hiring:** Recent breaches in Singapore fintech getting public attention
- Incident recovery is high-urgency signal
- CISO hiring post-incident = executive mandate
- Timeline is compressed (regulators + customer pressure)

---

## Success Definition: First Call

✅ **Qualified call:**
- You reached the decision-maker
- They confirmed hiring signal + timeline
- You scheduled a 30-min follow-up (discovery)
- They showed genuine interest (not "maybe later")

⭐ **OK call:**
- You reached someone who can talk
- They're evaluating timing
- They asked you to follow up next month
- Not hostile, not clearly interested

❌ **Poor call:**
- Wrong person, had to transfer
- They were dismissive
- You talked more than listened
- No clear next step agreed

---

## Pro Tips

1. **Reference their research.** "I saw you announced Series B in May..." → Instant credibility
2. **Listen for pain.** Let them talk. The pain point = your opening.
3. **Be specific.** "I help companies rebuild security post-incident" beats "I help with security"
4. **Don't pitch.** First call = discovery. Second call = suggest if fit.
5. **Get the date.** "Should we lock in 30 minutes next Wednesday at 3pm?" (get calendar invite)
6. **Follow up immediately.** Send meeting prep or case study within 2 hours of call
7. **Take notes.** "Biggest gap: people. Timeline: August hire" → Use in follow-up
8. **Tier Score matters.** Tier 1 (90+) gets same-day outreach. Tier 4 (<60) gets skipped.

---

**Print this. Keep on desk. Use it every day.**

**Questions? See detailed docs:**
- Airtable setup: `docs/airtable-setup.md`
- Tier Score: `docs/scoring-formula.md`
- Exa guide: `docs/exa-mcp-guide.md`
- Apollo guide: `docs/apollo-mcp-guide.md`
- Full workflow: `docs/ae-workflow-guide.md`
- Call templates: `docs/call-angle-templates.md`
- Test case: `docs/test-case.md`
