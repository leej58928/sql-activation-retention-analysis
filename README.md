# SQL Activation & Retention Analysis

## Overview
This project analyzes how early user activation impacts 30-day retention using SQL.
The objective is to evaluate whether users who engage meaningfully during their first week
are more likely to remain active in the long term.

All analysis was performed in Google BigQuery using user-level event data and
a modular SQL view-based pipeline.

---

## Data Description
The dataset consists of synthetic but realistically structured product usage data.

### users
- user_id
- signup_date

### events
- user_id
- event_time (DATE)
- event_type (e.g., login, core_feature, secondary_feature)

The data was intentionally generated to reflect heterogeneous user behavior,
including early engagement patterns and long-term retention differences.

---

## Metric Definitions

### Activation (Early Engagement)
A user is considered **activated** if, within the first 7 days after signup:
- The user triggered the core feature at least once, and
- The user was active on at least 2 distinct days

This definition emphasizes sustained early engagement rather than raw event volume.

---

### Retention (30-Day)
A user is considered **retained at 30 days** if:
- The user triggered at least one event on or after day 30 following signup

---

## Analysis Workflow
1. Identified events occurring within the first 7 days after signup
2. Aggregated early user activity metrics at the user level
3. Labeled users based on activation criteria
4. Labeled users based on 30-day retention
5. Compared retention outcomes between activated and non-activated users

Each step was implemented as a reusable SQL view.

---

## Key Findings

| Activation Status | Users | Retained Users | 30-Day Retention |
|------------------|-------|----------------|------------------|
| Not Activated    | 731   | 183            | 25.0%            |
| Activated        | 269   | 175            | 65.1%            |

Users who achieved early activation showed a **+40.1 percentage point lift**
in 30-day retention compared to non-activated users.
Activated users were more than **2.6× more likely** to be retained after 30 days.

---

## Business Implications
- Early activation is a strong leading indicator of long-term retention
- Improving onboarding and early feature discovery could yield significant downstream gains
- Activation metrics can be used as early signals for retention-focused interventions

---

## Tools & Skills
- SQL (CTEs, JOINs, aggregation, conditional logic)
- Google BigQuery
- Metric definition and validation
- Product and retention analytics
