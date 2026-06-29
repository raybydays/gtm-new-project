# GTM Security Hiring Research Workflow Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Set up Airtable-based lead research system for AEs to identify, enrich, and prepare discovery calls for prospects hiring security roles in Singapore.

**Architecture:** Single Airtable table (SecurityLeads) with manual workflow. AEs search Exa MCP for job openings, enrich with Apollo MCP, score via formula, research context, prepare discovery angle. No automation — human-driven research to ensure quality.

**Tech Stack:** Airtable (lead storage + scoring), Exa MCP (job search), Apollo MCP (email/phone enrichment), markdown guides

## Global Constraints

- Workflow is manual — AE controls trigger, no automated scraping
- Single Airtable table structure (SecurityLeads)
- Lead scoring formula must use job title tiers (Tier 1: 90-100, Tier 2: 70-89, Tier 3: 50-69, Tier 4: 30-49)
- Score multipliers: +15 (2+ roles), +10 (posted <7 days), +5 (company size >500)
- Contact enrichment via Apollo MCP (email + phone)
- Job data sourced from Exa MCP (XRCP)
- Call angle: consultative discovery, not hard sell
- Pain point signals: Compliance / Breach Recovery / Growth / Unknown

---

### Task 1: Create Airtable Base Structure

**Files:**
- Create: `docs/airtable-setup.md` (setup guide)
- Reference: CLAUDE.md (data model spec)

**Interfaces:**
- Produces: Airtable base `SecurityLeads` with 13 fields, ready for data entry

**Steps:**

- [ ] **Step 1: Create Airtable base**

Go to airtable.com, create new base named "GTM Security Hiring Research".

- [ ] **Step 2: Create SecurityLeads table**

In new base, rename default table to `SecurityLeads`.

- [ ] **Step 3: Add field: Company Name**

Field type: Text. Make this the primary field (default). Keep as identifier.

- [ ] **Step 4: Add field: Job Title**

Field type: Single Select. Add options:
- CISO
- Chief Information Security Officer
- VP/Head of Security
- Chief Security Officer
- VP/Head of Information Security
- Information Security Manager
- Senior Security Manager
- Security Operations Manager
- Security Director
- Chief Risk Officer
- Security Architect
- Senior Security Engineer
- Compliance Manager
- IT Security Manager
- Security Engineer
- SOC Analyst
- Security Analyst
- Risk Manager

- [ ] **Step 5: Add field: Posting Date**

Field type: Date. Format: "2026-06-29".

- [ ] **Step 6: Add field: Job URL**

Field type: URL.

- [ ] **Step 7: Add field: Hiring Manager**

Field type: Text.

- [ ] **Step 8: Add field: Email**

Field type: Email.

- [ ] **Step 9: Add field: Phone**

Field type: Phone Number (format: +65 XXXX XXXX for Singapore).

- [ ] **Step 10: Add field: Company Size**

Field type: Number. Label: "Employee Count".

- [ ] **Step 11: Add field: Tier Score**

Field type: Formula. Name: "Tier Score".

- [ ] **Step 12: Add field: Why Hiring Signal**

Field type: Single Select. Add options:
- Compliance
- Breach Recovery
- Growth
- Unknown

- [ ] **Step 13: Add field: Research Notes**

Field type: Long Text.

- [ ] **Step 14: Add field: Call Status**

Field type: Single Select. Add options:
- Prospect
- Researched
- Called
- Qualified
- Won
- Lost

- [ ] **Step 15: Add field: Call Angle**

Field type: Long Text.

- [ ] **Step 16: Add field: Next Action**

Field type: Text.

- [ ] **Step 17: Commit**

```bash
cd /Users/raymondchew/Documents/gtm-new-project
git add CLAUDE.md
git commit -m "docs: airtable setup guide and base structure"
```

---

### Task 2: Create Tier Score Formula

**Files:**
- Modify: Airtable SecurityLeads table
- Create: `docs/scoring-formula.md` (formula reference)

**Interfaces:**
- Consumes: Job Title field (Single Select), Posting Date field (Date), Company Size field (Number)
- Produces: Tier Score field (Formula) calculating: base score (30-100 by tier) + multipliers

**Steps:**

- [ ] **Step 1: Open Tier Score formula editor**

In Airtable SecurityLeads table, click the Tier Score field header → click "Edit field" → switch to "Formula" type.

- [ ] **Step 2: Create base score by job title**

Enter this formula:

```airtable
IF(
  OR(
    {Job Title} = "CISO",
    {Job Title} = "Chief Information Security Officer"
  ),
  90,
  IF(
    OR(
      {Job Title} = "VP/Head of Security",
      {Job Title} = "Chief Security Officer",
      {Job Title} = "VP/Head of Information Security"
    ),
    90,
    IF(
      OR(
        {Job Title} = "Information Security Manager",
        {Job Title} = "Senior Security Manager",
        {Job Title} = "Security Operations Manager",
        {Job Title} = "Security Director",
        {Job Title} = "Chief Risk Officer"
      ),
      75,
      IF(
        OR(
          {Job Title} = "Security Architect",
          {Job Title} = "Senior Security Engineer",
          {Job Title} = "Compliance Manager",
          {Job Title} = "IT Security Manager"
        ),
        60,
        IF(
          OR(
            {Job Title} = "Security Engineer",
            {Job Title} = "SOC Analyst",
            {Job Title} = "Security Analyst",
            {Job Title} = "Risk Manager"
          ),
          40,
          30
        )
      )
    )
  )
)
```

- [ ] **Step 3: Add recency multiplier**

Modify formula to add +10 for postings in last 7 days:

```airtable
IF(
  OR(
    {Job Title} = "CISO",
    {Job Title} = "Chief Information Security Officer"
  ),
  90,
  IF(
    OR(
      {Job Title} = "VP/Head of Security",
      {Job Title} = "Chief Security Officer",
      {Job Title} = "VP/Head of Information Security"
    ),
    90,
    IF(
      OR(
        {Job Title} = "Information Security Manager",
        {Job Title} = "Senior Security Manager",
        {Job Title} = "Security Operations Manager",
        {Job Title} = "Security Director",
        {Job Title} = "Chief Risk Officer"
      ),
      75,
      IF(
        OR(
          {Job Title} = "Security Architect",
          {Job Title} = "Senior Security Engineer",
          {Job Title} = "Compliance Manager",
          {Job Title} = "IT Security Manager"
        ),
        60,
        IF(
          OR(
            {Job Title} = "Security Engineer",
            {Job Title} = "SOC Analyst",
            {Job Title} = "Security Analyst",
            {Job Title} = "Risk Manager"
          ),
          40,
          30
        )
      )
    )
  )
) + IF(
  DATETIME_DIFF(TODAY(), {Posting Date}, 'days') <= 7,
  10,
  0
) + IF(
  {Company Size} > 500,
  5,
  0
)
```

- [ ] **Step 4: Save formula**

Click "Save" in formula editor.

- [ ] **Step 5: Test formula with sample row**

Enter test row:
- Company Name: "Test Corp"
- Job Title: "CISO"
- Posting Date: (today)
- Company Size: 1000

Expected: Tier Score = 90 + 10 + 5 = 105 (cap at 100 if needed, or leave as-is).

- [ ] **Step 6: Document formula**

Create `docs/scoring-formula.md`:

```markdown
# Tier Score Calculation

## Base Scores by Job Title

| Tier | Titles | Score |
|------|--------|-------|
| 1 | CISO, Chief Information Security Officer, VP/Head of Security, etc. | 90 |
| 2 | Information Security Manager, Senior Security Manager, etc. | 75 |
| 3 | Security Architect, Senior Security Engineer, Compliance Manager, etc. | 60 |
| 4 | Security Engineer, SOC Analyst, etc. | 40 |

## Multipliers

- +10 if posting date ≤ 7 days old
- +5 if company size > 500 employees

## Formula (Airtable)

See SecurityLeads table, Tier Score field.
```

- [ ] **Step 7: Commit**

```bash
git add docs/scoring-formula.md
git commit -m "feat: airtable tier score formula with recency and company size multipliers"
```

---

### Task 3: Create Exa MCP (XRCP) Integration Guide

**Files:**
- Create: `docs/exa-mcp-guide.md`

**Interfaces:**
- Produces: Step-by-step guide for AEs to search job openings using Exa MCP

**Steps:**

- [ ] **Step 1: Create Exa MCP guide**

Write `docs/exa-mcp-guide.md` with complete guide covering search queries, workflow, tips, and examples.

- [ ] **Step 2: Commit**

```bash
git add docs/exa-mcp-guide.md
git commit -m "docs: exa mcp job search and company research guide"
```

---

### Task 4: Create Apollo MCP Integration Guide

**Files:**
- Create: `docs/apollo-mcp-guide.md`

**Interfaces:**
- Produces: Step-by-step guide for AEs to enrich contacts using Apollo MCP

**Steps:**

- [ ] **Step 1: Create Apollo MCP guide**

Write `docs/apollo-mcp-guide.md` with complete guide covering enrichment workflow, batch processing, tips, and examples.

- [ ] **Step 2: Commit**

```bash
git add docs/apollo-mcp-guide.md
git commit -m "docs: apollo mcp email and phone enrichment guide"
```

---

### Task 5: Create AE Workflow Guide & Call Angle Templates

**Files:**
- Create: `docs/ae-workflow-guide.md`
- Create: `docs/call-angle-templates.md`

**Interfaces:**
- Produces: Complete workflow guide for AEs + reusable call angle templates

**Steps:**

- [ ] **Step 1: Create AE workflow guide**

Write `docs/ae-workflow-guide.md` covering all 4 phases (Search & Identify, Enrich & Verify, Prepare & Call, Track & Follow Up).

- [ ] **Step 2: Create call angle templates**

Write `docs/call-angle-templates.md` with 4 templates (Growth, Compliance, Breach Recovery, Generic) + customization tips + objection responses.

- [ ] **Step 3: Commit**

```bash
git add docs/ae-workflow-guide.md docs/call-angle-templates.md
git commit -m "docs: ae workflow guide and call angle templates for discovery calls"
```

---

### Task 6: End-to-End Workflow Test

**Files:**
- Create: `docs/test-case.md`
- Modify: Airtable SecurityLeads table

**Interfaces:**
- Consumes: All previous tasks (Airtable base, formulas, guides)
- Produces: Verified working workflow end-to-end + test case documentation

**Steps:**

- [ ] **Step 1: Create test case documentation**

Write `docs/test-case.md` with test scenario, steps, success criteria, troubleshooting.

- [ ] **Step 2: Perform end-to-end test**

Execute actual workflow: search Exa → add to Airtable → enrich with Apollo → verify scoring → write call angle.

- [ ] **Step 3: Document test result**

Add actual test run results to `docs/test-case.md`.

- [ ] **Step 4: Commit**

```bash
git add docs/test-case.md
git commit -m "test: end-to-end workflow test case with actual run results"
```

---

## Pre-Flight Review

**Scanning for conflicts...**

No conflicts found. All tasks are independent documentation/setup. Tasks can proceed in order. Plan is ready for execution.

---

**Tasks created. Starting Task 1 implementation.**
