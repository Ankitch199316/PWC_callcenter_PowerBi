# 📊 PwC Call Center Performance Dashboard (Power BI)

## Overview

This project presents a **Power BI reporting solution** built to analyze call center operations and customer experience. The dashboard converts raw call logs into **decision-ready insights** for operations managers and leadership, with a strong focus on efficiency, service quality, and agent performance.

---

## Business Objective

To enable stakeholders to:

* Monitor call center workload and peak periods
* Evaluate agent performance and resolution efficiency
* Track customer satisfaction and unanswered demand
* Identify operational gaps impacting service quality

---

## Key Business Questions Answered

* How many calls are received, answered, resolved, or abandoned?
* When do call volumes peak (by hour and day)?
* How fast are agents responding to customers?
* Which agents perform best on efficiency and resolution?
* Where are customers being underserved?

---
## Dashboard Preview
<img width="1917" height="1005" alt="dashboard screenshots" src="https://github.com/user-attachments/assets/8283abac-89d5-480c-b7b0-143ea62a2956" />


---

## Dashboard Highlights

* Executive-level KPI overview (Calls, Resolve %, Abandon Rate, CSAT)
* Time-based analysis (hourly & weekly call patterns)
* Agent performance comparison
* Customer satisfaction segmentation
* Clean, branded layout inspired by PwC design standards

---

## Data Preparation & Modeling

All transformations were handled inside **Power BI (Power Query + DAX)**.

**Key steps:**

* Standardized regional settings (English – US) for date/time accuracy
* Removed duplicate Call IDs
* Renamed columns for semantic clarity
* Merged date and time into a unified timestamp
* Engineered:

  * Call Hour
  * Day Name
  * Satisfaction Categories (via `SWITCH`)
* Handled null satisfaction values as **“Not Served”**

---

## Core Measures (DAX)

* Total Calls (distinct Call ID)
* Call Resolve %
* Abandon Rate
* Average Speed of Answer
* Customer Satisfaction Score (0–100%)

---

## Design & Reporting Approach

* Layout designed externally and applied as a background for consistency
* Focus on **clarity over decoration**
* Visual hierarchy optimized for executive consumption
* Report structured for quick scanning and drill-down analysis

---

## Files Included

* 📄 Dashboard PDF (static report)
* 📊 Raw dataset
* 🖼 Dashboard screenshots
* 🧮 DAX documentation (key measures)

---

## Tools Used

* Power BI Desktop
* Power Query
* DAX
* PowerPoint (layout design)

---

## Intended Audience

* Operations Managers
* Business Analysts
* Reporting & Dashboard Specialists
* CX / Call Center Leadership

---

