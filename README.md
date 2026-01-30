# Aviation Operations Retention & Reliability Analysis (SQL)

## Project Overview

This project analyzes aviation operational data to understand how service disruptions and operational reliability influence customer retention behavior.  
The goal is to transform raw operational records into measurable retention signals and identify which operational failures create the highest downstream customer risk.

Rather than treating retention as a purely marketing metric, this project frames retention as an operational outcome tied directly to system reliability.

---

## Business Problem

In aviation operations, disruptions such as delays, cancellations, or irregular handling degrade customer trust.  
When reliability drops, repeat usage declines — but the relationship is rarely quantified at an operational level.

The central hypothesis:

**Operational instability predicts customer retention risk.**

This project builds a structured SQL analytics pipeline to measure how disruption patterns correlate with retention behavior.

---

## Data Model

The dataset contains operational aviation records including:

- flight performance and delay indicators
- cancellation and irregular operations
- customer interaction and repeat behavior markers

To support retention analysis, I constructed an analytical pipeline that aggregates raw event-level data into customer-level and route-level performance signals.

Key engineered components include:

- disruption frequency per customer
- repeat usage behavior
- delay severity metrics
- operational reliability scores

This mirrors how aviation analytics teams structure retention risk models.

---

## Analytical Approach

### 1. Operational reliability metrics

I calculated disruption indicators including delay frequency, cancellation events, and severe irregular operations.

These metrics convert operational noise into structured risk variables.

---

### 2. Retention behavior modeling

Customers were segmented based on repeat usage patterns following disruption exposure.

This allows comparison between:

- stable experience cohorts
- disruption-heavy cohorts

to observe behavioral divergence.

---

### 3. Risk concentration analysis

I identified whether retention risk is evenly distributed or concentrated within specific operational patterns.

This step determines where intervention produces the highest impact.

---

## Results

The analysis revealed:

- Customers exposed to repeated disruptions show significantly lower repeat engagement
- Severe disruptions create long-term retention damage, not just short-term dissatisfaction
- Reliability risk is concentrated within identifiable operational patterns rather than random noise
- A small subset of high-disruption events drives disproportionate retention loss

This confirms that retention is an operational analytics problem, not only a marketing problem.

---

## Key Insights & Actions

### Insight 1 — Disruption exposure predicts churn risk

Customers experiencing repeated operational instability show measurable retention decline.

**Action:**  
Build early-warning dashboards that flag high-risk disruption clusters and trigger proactive customer recovery strategies.

---

### Insight 2 — Severe events have outsized behavioral impact

A small number of high-severity disruptions drive a large share of retention loss.

**Action:**  
Prioritize recovery resources for severe operational failures instead of treating all disruptions equally.

---

### Insight 3 — Retention risk is structurally concentrated

Risk is not random; it follows repeatable operational patterns.

**Action:**  
Shift analytics from reactive reporting to predictive monitoring of reliability hotspots.

---

## Business Impact

This framework enables aviation operations teams to:

- detect retention risk early
- prioritize operational recovery investment
- protect long-term customer value
- align reliability metrics with business outcomes

The project demonstrates how operational analytics can directly inform retention strategy.

---

## Tools & Skills Demonstrated

Advanced SQL • Aggregations • Multi-table joins  
Customer retention analytics • Operational reliability modeling  
Decision-oriented analytics
