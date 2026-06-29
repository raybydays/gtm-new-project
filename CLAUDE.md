# GTM Security Hiring Research Workflow

## Project Overview

B2B GTM engineering workflow for Account Executives (AEs) at LRQA. AEs research companies hiring for security roles in Singapore to identify budget signals and pain points, then conduct discovery calls to uncover security posture vulnerabilities for pen testing services.

**Core insight:** Companies actively hiring for security roles = confirmed budget + acknowledged security investment need.

## Goals

1. Enable AEs to identify hot leads based on security job postings
2. Enrich lead data with contact info + company context
3. Arm AEs with discovery angle + research before calls
4. Discover underlying pain points (compliance-driven, breach recovery, growth)
5. Prepare AEs to pitch pen testing as strategic discovery tool

## Success Criteria

- AE can search, score, and enrich leads in <30 min per target
- Contact info (email + phone) auto-populated via Apollo MCP
- Call angle + research notes prepared before outreach
- Pain point hypothesis documented (compliance/breach/growth)
- Lead scoring formula consistently identifies tier-1 prospects (CISO/VP Security level)

## Lead Scoring Framework

**Job Title Tiers:**

| Tier | Titles | Base Score |
|------|--------|-----------|
| 1 (Hot) | CISO, Chief Information Security Officer, VP/Head of Security, Chief Security Officer, VP/Head of Information Security | 90-100 |
| 2 (Good) | Information Security Manager, Senior Security Manager, Security Operations Manager, Security Director, Chief Risk Officer (if security reports to them) | 70-89 |
| 3 (Decent) | Security Architect, Senior Security Engineer, Compliance Manager, IT Security Manager | 50-69 |
| 4 (Low) | Security Engineer, SOC Analyst, Security Analyst, Risk Manager | 30-49 |

**Multipliers:**
- +15 points if 2+ open security roles in company (scaling security)
- +10 points if posted in last 7 days (urgent hiring signal)
- +5 points if company size >500 employees (bigger budgets)

## Data Model

**Single Airtable Table:** `SecurityLeads`

| Field | Type | Purpose |
|-------|------|---------|
| Company Name | Text | Unique identifier |
| Job Title | Single Select | Links to scoring tier |
| Posting Date | Date | Recency signal |
| Job URL | URL | Reference link |
| Hiring Manager | Text | Name of job poster |
| Email | Email | Apollo MCP output |
| Phone | Phone | Apollo MCP output |
| Company Size | Number | Employee count |
| Tier Score | Number | Auto-calculated formula |
| Why Hiring Signal | Single Select | Compliance / Breach Recovery / Growth / Unknown |
| Research Notes | Long Text | AE discovery findings |
| Call Status | Single Select | Prospect → Researched → Called → Qualified → Won/Lost |
| Call Angle | Long Text | Personalized discovery message |
| Next Action | Text | Follow-up steps |

**Tier Score Formula (Airtable):**
```
IF({Job Title}="CISO", 90, 
   IF({Job Title}="VP Security", 90, 
      IF({Job Title}="Head of Security", 85, 
         ...)))
+ IF({Multiple Openings}, 15, 0)
+ IF(DATETIME_DIFF(TODAY(), {Posting Date}, 'days') < 7, 10, 0)
+ IF({Company Size} > 500, 5, 0)
```

## Workflow (Manual)

1. **Search:** AE uses Exa MCP (XRCP) to search "Singapore security job openings" + filters by title tier
2. **Add to Airtable:** Copy relevant postings to SecurityLeads table
3. **Enrich:** Run Apollo MCP batch enrichment to pull emails + phone numbers
4. **Score:** Airtable formula auto-calculates Tier Score
5. **Research:** AE manually researches company + hiring context
   - Why hiring now? (compliance, breach recovery, growth scaling?)
   - Who's the decision maker? (CISO/VP/Manager?)
   - What's their current security posture signal?
6. **Prepare:** AE writes Call Angle and Research Notes
7. **Call:** AE reaches out with discovery angle: "You're investing in security talent. Let's understand your environment so your new hires can make immediate impact."

## Call Angle

**Core message:** Consultative discovery, not hard sell.

Position pen testing as a **strategic discovery tool** to inform security hiring and investment:
- "You're hiring for security roles — that signals budget + pain point"
- "Before new hires start, validate current posture"
- "Let's identify gaps so your new team focuses on what matters"
- "Understand vulnerabilities now so you're not surprised later"

**Goal:** Uncover hidden pain points and security posture awareness that justifies pen testing engagement.

## Tech Stack

| Component | Tool | Purpose |
|-----------|------|---------|
| Job Data Scraping | Exa MCP (XRCP) | Search + scrape job postings, company research |
| Contact Enrichment | Apollo MCP | Email + phone lookup for hiring managers |
| Lead Storage | Airtable | Single table, manual workflow, lead scoring |
| Workflow Trigger | Manual | AE initiates search, enrichment, research |

**Setup:** Apollo MCP already installed globally.

## MCP Integration Notes

- **Exa MCP:** Search for Singapore security job openings, scrape company websites for additional context (funding, team size, recent news)
- **Apollo MCP:** Batch enrich emails + phone numbers. Input: company name + hiring manager name. Output: contact info.

## Future Considerations (Out of Scope)

- Automated daily job scraping + alerts
- CRM sync (HubSpot/Salesforce)
- Outreach automation (email templates, sequences)
- Compliance tracking (SOC2, ISO certifications as additional multipliers)
- Geographic expansion beyond Singapore
