# GTM Security Hiring Research Workflow

B2B GTM engineering workflow for Account Executives to research companies hiring for security roles in Singapore. Identify budget signals, enrich lead data, and prepare discovery calls to uncover security posture vulnerabilities for pen testing services.

**Core insight:** Companies actively hiring for security roles = confirmed budget + acknowledged security investment need.

## Quick Start

1. **Search jobs** → Use Exa MCP to search Singapore security job openings
2. **Add leads** → Copy postings to Airtable SecurityLeads table
3. **Enrich contacts** → Run Apollo MCP batch to pull emails + phone numbers
4. **Score leads** → Airtable formula auto-calculates tier scores
5. **Research** → Identify why they're hiring (compliance, breach, growth)
6. **Prepare call** → Write research notes + discovery angle
7. **Call** → Consultative discovery, not hard sell

Time per lead: ~30 minutes (search → enrich → research → ready to call)

## Lead Scoring Framework

### Job Title Tiers

| Tier | Titles | Base Score |
|------|--------|-----------|
| 1 (Hot) | CISO, Chief Information Security Officer, VP/Head of Security, Chief Security Officer | 90-100 |
| 2 (Good) | Information Security Manager, Senior Security Manager, Security Operations Manager, Security Director | 70-89 |
| 3 (Decent) | Security Architect, Senior Security Engineer, Compliance Manager, IT Security Manager | 50-69 |
| 4 (Low) | Security Engineer, SOC Analyst, Security Analyst, Risk Manager | 30-49 |

### Scoring Multipliers

- **+15 pts** — 2+ open security roles (scaling security team)
- **+10 pts** — Posted in last 7 days (urgent hiring)
- **+5 pts** — Company size >500 employees (bigger budgets)

**Formula:**
```
Base Score 
+ (Multiple Openings ? 15 : 0)
+ (Posted < 7 days ? 10 : 0)
+ (Company Size > 500 ? 5 : 0)
```

## Data Model

Single Airtable table: `SecurityLeads`

| Field | Type | Purpose |
|-------|------|---------|
| Company Name | Text | Unique identifier |
| Job Title | Single Select | Links to scoring tier |
| Posting Date | Date | Recency signal |
| Job URL | URL | Reference link |
| Hiring Manager | Text | Contact name |
| Email | Email | Apollo MCP enrichment |
| Phone | Phone | Apollo MCP enrichment |
| Company Size | Number | Employee count |
| Tier Score | Number | Auto-calculated formula |
| Why Hiring Signal | Single Select | Compliance / Breach Recovery / Growth / Unknown |
| Research Notes | Long Text | AE findings (security posture, budget, pain points) |
| Call Status | Single Select | Prospect → Researched → Called → Qualified → Won/Lost |
| Call Angle | Long Text | Personalized discovery message |
| Next Action | Text | Follow-up steps |

## Workflow Steps

### 1. Search & Identify
Use **Exa MCP** to search:
```
"Singapore security job openings" 
+ filter by job title tier (CISO, VP Security, etc.)
```

### 2. Add to Airtable
Copy relevant postings to SecurityLeads table with:
- Company name
- Job title
- Posting date
- Job URL
- Hiring manager name

### 3. Enrich Contacts
Run **Apollo MCP** batch enrichment:
- Input: company name + hiring manager name
- Output: email + phone number

### 4. Auto-Score
Airtable formula calculates Tier Score based on:
- Job title tier (base)
- Multiple openings (+15)
- Recency (+10)
- Company size (+5)

### 5. Research
AE manually investigates:
- Why is company hiring now? (compliance audit, breach recovery, growth scaling?)
- Who's the decision maker? (CISO/VP/Manager?)
- Current security posture signals?
- Recent news, funding, team changes?
- Compliance requirements? (ISO, SOC2, GDPR?)

### 6. Prepare Call Angle
Document in Airtable:
- **Research Notes** — findings from step 5
- **Call Angle** — personalized discovery message
- **Why Hiring Signal** — categorize the pain point

### 7. Call
Reach out with consultative discovery:

> "You're investing in security talent. Before your new hires start, let's validate your current environment. A quick security discovery call will help them focus on what matters most and avoid surprises down the road."

**Goal:** Uncover hidden vulnerabilities and security posture gaps that justify pen testing engagement.

## Call Angle Template

Position pen testing as a **strategic discovery tool** to support security hiring:

- **Opening:** "You're hiring for security roles — that signals budget + acknowledged security need"
- **Discovery:** "Before new hires start, understand your current environment"
- **Value:** "Validate gaps so your new team focuses on what matters"
- **Outcome:** "Uncover vulnerabilities now, not in production"

See `docs/call-angle-templates.md` for full call angle library by hiring signal.

## Tech Stack

| Component | Tool | Purpose |
|-----------|------|---------|
| Job Search | [Exa MCP](docs/exa-mcp-guide.md) | Search + scrape job postings, company context |
| Contact Enrichment | [Apollo MCP](docs/apollo-mcp-guide.md) | Email + phone lookup for hiring managers |
| Lead Database | Airtable | Single table, manual workflow, auto-scoring |
| AE Workflow | Manual | Search → enrich → research → call |

**Setup:**
- Apollo MCP installed globally
- Airtable base created with SecurityLeads table
- Exa MCP configured for Singapore job searches

## Documentation

- `CLAUDE.md` — Project requirements & specifications
- `docs/airtable-setup.md` — Airtable table creation & formula setup
- `docs/exa-mcp-guide.md` — Exa search syntax & tips
- `docs/apollo-mcp-guide.md` — Apollo batch enrichment workflow
- `docs/scoring-formula.md` — Tier score formula breakdown
- `docs/call-angle-templates.md` — Call angle library by pain point
- `docs/ae-workflow-guide.md` — Full AE workflow playbook
- `docs/ae-workflow-quick-reference.md` — Quick reference card
- `docs/test-case.md` — End-to-end workflow test case

## Setup Instructions

### Prerequisites
- Airtable workspace + API access
- Apollo MCP installed & configured
- Exa MCP installed & configured
- GitHub access to clone this repo

### Initial Setup
1. Clone this repo
2. Follow `docs/airtable-setup.md` to create SecurityLeads table
3. Configure Apollo MCP with your API key
4. Configure Exa MCP for Singapore searches
5. Share Airtable base with AE team
6. Review `docs/ae-workflow-quick-reference.md` with team

### First Lead Search
1. Open Airtable SecurityLeads table
2. Use Exa MCP to search "Singapore security job openings"
3. Copy top 3 results to Airtable
4. Run Apollo MCP to enrich contacts
5. Review auto-scored tier rankings
6. Follow test case in `docs/test-case.md` to verify workflow

## Success Criteria

- ✅ AE can search, score, enrich leads in <30 min per target
- ✅ Contact info (email + phone) auto-populated via Apollo
- ✅ Call angle + research notes prepared before outreach
- ✅ Pain point hypothesis documented (compliance/breach/growth)
- ✅ Tier score formula consistently identifies CISO/VP Security leads

## Common Pain Point Signals

| Signal | What to Ask | What They Need |
|--------|-------------|----------------|
| **Compliance Hiring** | "Are you preparing for SOC2/ISO audit?" | Proof of security controls, compliance roadmap |
| **Breach Recovery** | "Recently faced security incident?" | Vulnerability assessment, incident response playbook |
| **Growth Scaling** | "Expanding security for business growth?" | Architecture review, threat modeling, risk assessment |
| **Acquisition/M&A** | "Recent acquisition or being acquired?" | Security due diligence, vendor assessment |

## Future Enhancements

Out of scope for v1, but documented for roadmap:
- Automated daily job scraping + Slack alerts
- CRM sync (HubSpot/Salesforce)
- Outreach automation (email sequences)
- Compliance multipliers (SOC2, ISO certifications)
- Geographic expansion beyond Singapore

## License

MIT License — see LICENSE file

## Contributing

This workflow is tailored for LRQA Account Executives. To adapt for your org:
1. Modify job title tiers in `docs/scoring-formula.md`
2. Customize call angles in `docs/call-angle-templates.md`
3. Update target geography in Exa search filters
4. Review test case and run end-to-end before rollout

## Support

- See `docs/ae-workflow-guide.md` for full workflow details
- Check `docs/test-case.md` to verify setup works
- Review CLAUDE.md for project specifications
