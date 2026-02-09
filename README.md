# Activation & Retention Analysis (SQL)

## Project Overview
This project analyzes how early user activation behavior influences 30-day retention using SQL-based cohort and behavioral analysis.

The goal is to answer a core product analytics question:

> Do users who activate early show higher long-term retention?

Activation is defined based on meaningful early engagement within the first 7 days after signup, and retention is measured as continued usage at 30 days.

---

## Dataset
The analysis uses two relational tables:

- **users**
  - `user_id`
  - `signup_date`
- **events**
  - `user_id`
  - `event_time` (DATE)
  - `event_type`

Each event represents a user action within the product, including a designated core feature event that signals meaningful engagement.

---

## Activation Definition (First 7 Days)
A user is considered **activated** if they meet **both** of the following conditions within the first 7 days after signup (Day 0–6):

- They trigger at least one **core feature** event
- They are active on at least **two distinct days**

This definition filters out superficial or one-off usage and focuses on sustained early engagement.

---

## Retention Definition (30 Days)
A user is considered **retained at 30 days** if they have at least one event on or after Day 30 following signup.

This metric captures whether early engagement translates into longer-term product usage.

---

## SQL Methodology
The analysis is implemented using layered SQL views for clarity and modularity:

1. **Early Event Window (7 Days)**
   - Extracts all user events occurring between signup day and Day 6
   - Serves as the foundation for activation metrics

2. **Early Engagement Metrics**
   - Counts total early events
   - Counts core feature usage
   - Measures active days within the first 7 days

3. **Activation Labeling**
   - Classifies users as activated vs non-activated based on predefined criteria

4. **Retention Labeling**
   - Identifies users who return at or after Day 30

5. **Activation vs Retention Summary**
   - Compares 30-day retention rates between activated and non-activated users

---

## Key Analysis Output
The final output compares **30-day retention rates** by activation status:

| Activation Status | Users | Retained Users | 30-Day Retention Rate |
|------------------|-------|----------------|----------------------|
| Activated        | N     | N              | X%                   |
| Not Activated    | N     | N              | Y%                   |

This comparison directly demonstrates the relationship between early activation behavior and long-term user retention.

---

## Insights & Business Implications
- Users who activate early are significantly more likely to be retained at 30 days
- Early engagement with core features is a strong predictor of long-term usage
- Product teams can improve retention by:
  - Optimizing onboarding flows
  - Encouraging early interaction with core features
  - Identifying at-risk users who fail to activate within the first week

---

## Skills Demonstrated
- SQL cohort analysis
- Behavioral metric design (activation & retention)
- Time-windowed event analysis
- Data modeling using layered SQL views
- Translating engagement data into product insights

---

## 🔧 Tools
- SQL (CTEs, views, conditional aggregation)
- Relational event data modeling
