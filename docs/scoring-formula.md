# Tier Score Formula for Airtable

## Overview

The **Tier Score** is an automated Airtable formula that ranks security job postings based on the seniority level of the position and signals of urgency/scale. This formula enables Account Executives to quickly identify the highest-value prospects within their lead pipeline.

### Formula Logic

The formula combines three scoring dimensions:

1. **Base Score** (0-90 points): Job title seniority tier
2. **Recency Multiplier** (+10 points): Posted within last 7 days
3. **Scale Multiplier** (+5 points): Company has 500+ employees

**Maximum possible score:** 105 points  
**Minimum possible score:** 0 points

---

## Job Title Tier Breakdown

### Tier 1: Executive/Strategic (Base Score: 90)
**Rationale:** C-suite and VP-level roles have complete budget authority and direct ownership of security strategy.

| Job Title | Variations |
|-----------|-----------|
| CISO | Chief Information Security Officer |
| VP/Head of Security | Chief Security Officer, VP of Information Security, Head of Information Security |

**Why it matters:** These are your "hot" leads. They own the security budget, have hiring authority, and can unilaterally approve pen testing engagements.

---

### Tier 2: Management/Director (Base Score: 75)
**Rationale:** Managers and directors control budget allocation and hiring for their teams. They can greenlight discovery work but may need executive approval.

| Job Title | Variations |
|-----------|-----------|
| Information Security Manager | Senior Security Manager |
| Security Operations Manager | Security Director |
| Chief Risk Officer | (when security reports to them) |

**Why it matters:** These are "good" leads. They have hands-on ownership of security operations and can initiate conversations about security posture.

---

### Tier 3: Senior Technical (Base Score: 60)
**Rationale:** Senior individual contributors have deep technical insight into security gaps but limited budget authority. They influence purchasing decisions.

| Job Title | Variations |
|-----------|-----------|
| Security Architect | Senior Security Engineer |
| Compliance Manager | IT Security Manager |

**Why it matters:** These are "decent" leads. They can identify technical gaps and recommend solutions, but require management approval.

---

### Tier 4: Individual Contributor (Base Score: 40)
**Rationale:** Entry to mid-level engineers/analysts execute security work but have limited authority or visibility into broader initiatives.

| Job Title | Variations |
|-----------|-----------|
| Security Engineer | SOC Analyst |
| Security Analyst | Risk Manager |

**Why it matters:** These are "low-priority" leads. They may be valuable for implementation details, but won't have authority to engage pen testing services.

---

## Multipliers

### Recency Multiplier: +10 Points
**Condition:** Posting date ≤ 7 days old

**Why it matters:** Fresh job postings indicate:
- Active hiring (budget confirmed)
- Urgent security needs
- Less likely to have already filled the role
- Higher urgency = more likely to engage with discovery services

**Formula logic:** `IF(DATETIME_DIFF(TODAY(), {Posting Date}, 'days') < 7, 10, 0)`

---

### Company Size Multiplier: +5 Points
**Condition:** Company has more than 500 employees

**Why it matters:** Larger companies typically have:
- Dedicated security teams
- Larger security budgets
- More complex environments requiring pen testing
- Higher deal sizes and longer sales cycles

**Formula logic:** `IF({Company Size} > 500, 5, 0)`

---

## Complete Airtable Formula

### Copy-Paste Formula

```
(
IF({Job Title}="CISO", 90,
IF({Job Title}="Chief Information Security Officer", 90,
IF({Job Title}="VP Security", 90,
IF({Job Title}="Head of Security", 90,
IF({Job Title}="Chief Security Officer", 90,
IF({Job Title}="VP of Information Security", 90,
IF({Job Title}="Head of Information Security", 90,
IF({Job Title}="Information Security Manager", 75,
IF({Job Title}="Senior Security Manager", 75,
IF({Job Title}="Security Operations Manager", 75,
IF({Job Title}="Security Director", 75,
IF({Job Title}="Chief Risk Officer", 75,
IF({Job Title}="Security Architect", 60,
IF({Job Title}="Senior Security Engineer", 60,
IF({Job Title}="Compliance Manager", 60,
IF({Job Title}="IT Security Manager", 60,
IF({Job Title}="Security Engineer", 40,
IF({Job Title}="SOC Analyst", 40,
IF({Job Title}="Security Analyst", 40,
IF({Job Title}="Risk Manager", 40, 0)))))))))))))))))))))))
)
+
IF(DATETIME_DIFF(TODAY(), {Posting Date}, 'days') < 7, 10, 0)
+
IF({Company Size} > 500, 5, 0)
```

### Key Features

- **Nested IF statements** map each job title to its tier score
- **DATETIME_DIFF** calculates days between posting date and today
- **Default value of 0** if job title doesn't match any category (prevents errors)
- **Separate addition** of multipliers for clarity and maintainability
- **No special characters** or formatting that could break Airtable parsing

---

## Step-by-Step Airtable Implementation

### Prerequisites

Before implementing this formula, ensure your `SecurityLeads` table includes:
- **Job Title** field (Single Select type)
- **Posting Date** field (Date type)
- **Company Size** field (Number type)
- **Tier Score** field (Number type)

### Implementation Steps

1. **Open your Airtable base** and navigate to the `SecurityLeads` table

2. **Locate the Tier Score field**
   - Click on the field header
   - Select "Edit Field" (or pencil icon)

3. **Change field type to Formula** (if not already)
   - Field type dropdown → Select "Formula"

4. **Paste the complete formula** from above into the formula editor
   - Click in the formula textarea
   - Clear any existing content (Ctrl+A / Cmd+A)
   - Paste the full formula from the "Copy-Paste Formula" section

5. **Verify field references**
   - Ensure `{Job Title}`, `{Posting Date}`, and `{Company Size}` exactly match your field names
   - Field names are case-sensitive in Airtable
   - If your fields have different names, replace them in the formula

6. **Click "Save"**
   - Airtable will validate the formula syntax
   - You should see a green checkmark if successful

7. **Test with sample records** (see Testing section below)

### Important Notes

- **Field names are case-sensitive** in Airtable formulas
- **Single Select options** must exactly match the IF conditions (including capitalization)
- If a field name contains special characters, wrap it in curly braces: `{Field Name}`
- The formula calculates automatically whenever source fields change

---

## Testing Instructions

### Test Case 1: Executive with Fresh Posting, Large Company
**Scenario:** CISO role posted yesterday at a 800-person company

**Setup:**
- Job Title: `CISO`
- Posting Date: Yesterday (1 day ago)
- Company Size: `800`

**Expected Score:** 105
- Base score: 90 (CISO = Tier 1)
- Recency: +10 (posted < 7 days ago)
- Company size: +5 (>500 employees)
- **Total: 90 + 10 + 5 = 105**

**Verification:** Check that the Tier Score field shows `105`

---

### Test Case 2: Manager Role, Aged Posting, Small Company
**Scenario:** Security Manager role posted 10 days ago at a 200-person company

**Setup:**
- Job Title: `Information Security Manager`
- Posting Date: 10 days ago
- Company Size: `200`

**Expected Score:** 75
- Base score: 75 (Security Manager = Tier 2)
- Recency: +0 (posted > 7 days ago)
- Company size: +0 (≤500 employees)
- **Total: 75 + 0 + 0 = 75**

**Verification:** Check that the Tier Score field shows `75`

---

### Test Case 3: Architect Role, Recent Posting, Enterprise Company
**Scenario:** Security Architect role posted 5 days ago at a 1000-person company

**Setup:**
- Job Title: `Security Architect`
- Posting Date: 5 days ago
- Company Size: `1000`

**Expected Score:** 75
- Base score: 60 (Security Architect = Tier 3)
- Recency: +10 (posted < 7 days ago)
- Company size: +5 (>500 employees)
- **Total: 60 + 10 + 5 = 75**

**Verification:** Check that the Tier Score field shows `75`

---

### Test Case 4: Engineer Role, Old Posting, Small Company
**Scenario:** Security Engineer posted 30 days ago at a 150-person company

**Setup:**
- Job Title: `Security Engineer`
- Posting Date: 30 days ago
- Company Size: `150`

**Expected Score:** 40
- Base score: 40 (Security Engineer = Tier 4)
- Recency: +0 (posted > 7 days ago)
- Company size: +0 (≤500 employees)
- **Total: 40 + 0 + 0 = 40**

**Verification:** Check that the Tier Score field shows `40`

---

### Test Case 5: VP Security, Today Posting, Boundary Company
**Scenario:** VP Security posted today at exactly 500-person company

**Setup:**
- Job Title: `VP Security`
- Posting Date: Today
- Company Size: `500`

**Expected Score:** 100
- Base score: 90 (VP Security = Tier 1)
- Recency: +10 (posted < 7 days ago)
- Company size: +0 (exactly 500, not >500)
- **Total: 90 + 10 + 0 = 100**

**Verification:** Check that the Tier Score field shows `100`

---

## Troubleshooting Guide

### Issue: Formula shows error "#ERROR!"

**Possible causes:**
1. **Mismatched field names** – Field names in formula don't match actual field names
   - **Fix:** Click field header → Edit Field → Copy exact field name
   - Verify: `{Job Title}`, `{Posting Date}`, `{Company Size}` match your table

2. **Wrong field type** – Source fields are wrong type
   - **Fix:** Ensure:
     - `Job Title` is **Single Select** type
     - `Posting Date` is **Date** type
     - `Company Size` is **Number** type

3. **Extra spaces in formula** – Pasted formula has invisible characters
   - **Fix:** Delete formula, re-copy from above, paste carefully

**Resolution steps:**
- Clear the formula field entirely
- Copy the formula text again
- Paste slowly and check for any typos
- Verify all curly braces `{}` are present
- Click Save

---

### Issue: All scores are 0 even for known CISO roles

**Possible cause:**
- Job Title field contains values that don't exactly match formula conditions
- Example: Formula checks for `"CISO"` but field contains `"CISO "` (trailing space)

**Fix:**
- Check Job Title field options against formula conditions
- Standardize job title names to remove extra spaces
- Update Job Title Single Select options to match formula exactly

**Verification:**
- Click Job Title field → Edit Field → View all options
- Compare with job titles in the formula
- Edit options to match formula case-sensitivity

---

### Issue: Recency multiplier not applying (all +10 or all +0)

**Possible cause:**
- `Posting Date` field contains text instead of actual dates
- Date format mismatch

**Fix:**
- Ensure `Posting Date` field type is **Date** (not Text)
- Dates should be formatted as actual date values, not text strings
- Re-enter dates using Airtable's date picker

**Verification:**
- Edit a record's `Posting Date` field
- Confirm it opens a date picker (not text input)

---

### Issue: Company Size multiplier not working

**Possible cause:**
- `Company Size` field contains text or formatted numbers
- Example: `"500,000"` instead of `500000`

**Fix:**
- Ensure `Company Size` field type is **Number** (not Text)
- Remove any commas or currency symbols
- Re-enter values as pure numbers

**Verification:**
- Edit a record's `Company Size` field
- Confirm it opens a number input (not text input)

---

### Issue: Scores are slightly off (e.g., 74 instead of 75)

**Possible cause:**
- Posting date is exactly 7 days old
- Formula uses strict `<` (less than), not `<=`

**Check:**
- Verify the posting date
- If exactly 7 days old, recency bonus won't apply (this is intentional)
- Formula is: `DATETIME_DIFF(TODAY(), {Posting Date}, 'days') < 7`
- This means "less than 7 days" = 0-6 days inclusive

---

## Formula Maintenance

### Updating Job Titles

If you need to add or modify job titles:

1. **Add new Single Select option** to Job Title field
2. **Update formula** to include the new title
3. **Add new IF statement** with appropriate base score

**Example:**
To add "Director of Security Operations" (Tier 2):
```
IF({Job Title}="Director of Security Operations", 75, ...
```

### Adjusting Multipliers

To change a multiplier value:

1. **Identify the multiplier line** in the formula
2. **Update the number** in the IF statement
3. **Document the change** for other team members

**Example:**
To change recency bonus from +10 to +15:
```
IF(DATETIME_DIFF(TODAY(), {Posting Date}, 'days') < 7, 15, 0)
```

### Adding New Multipliers

To add a new multiplier (e.g., multiple open roles):

1. **Create new field** in Airtable table (e.g., "Number of Open Roles")
2. **Add to formula** as new addition:
```
+ IF({Number of Open Roles} >= 2, 15, 0)
```
3. **Test** with sample records

---

## Formula Performance Notes

- **Calculation time:** Instantaneous (nested IF functions are lightweight)
- **Recalculation:** Automatic whenever Job Title, Posting Date, or Company Size change
- **No dependencies:** Formula only reads from the current record, no cross-record lookups
- **Scaling:** Works efficiently with 1000+ records

---

## Success Criteria Checklist

Before deploying to your team:

- [ ] All job titles in your table exactly match formula conditions
- [ ] Posting Date field is Date type (not Text)
- [ ] Company Size field is Number type (not Text)
- [ ] All 5 test cases pass with expected scores
- [ ] Formula calculates automatically on new records
- [ ] Team members understand the scoring logic
- [ ] You have a backup of your Airtable base

---

## Related Documentation

- **Airtable Setup:** See `airtable-setup.md` for full table structure
- **Workflow Guide:** See GTM workflow document for how to use Tier Score in lead prioritization
- **MCP Integration:** See `docs/apollo-enrichment.md` for contact enrichment workflow

