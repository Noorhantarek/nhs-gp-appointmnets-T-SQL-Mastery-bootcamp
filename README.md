# NHS GP Appointments: DNA Analysis with T-SQL# NHS GP Appointments: DNA Analysis with T-SQL

## Project Overview

This project was completed as part of the **T-SQL Mastery Bootcamp Capstone Project**.

Using NHS open data on GP appointments, I explored **Did Not Attend (DNA)** patterns across different appointment modes during 2025.

The project gave me an opportunity to apply and consolidate several SQL concepts, including:

* Aggregation with `SUM()`
* Conditional aggregation using `CASE WHEN`
* Grouping data over time
* Subqueries
* Window aggregate functions
* `PARTITION BY`
* Percentage calculations
* Handling zero denominators with `NULLIF()`

The analysis focuses on two related questions:

1. **How do DNA rates compare across different appointment modes, and how do these rates change month by month during 2025?**
2. **Within each month, what proportion of DNA appointments comes from each appointment mode?**

---

## Dataset

The analysis uses **NHS open data on GP appointments**, accessed within the bootcamp's SQL environment.

The main fields used were:

* `Effective_Snapshot_Date`
* `Appointment_Mode`
* `Appointment_Status`
* `Count`

The analysis was restricted to appointments recorded during **2025**.

---

# Analysis 1 — DNA Rate by Appointment Mode

## Question

**How do DNA rates compare across different appointment modes, such as Face-to-Face, Telephone and Video, and how does this change month by month during 2025?**

For each month and appointment mode, I calculated:

* Total number of appointments
* Number of DNA appointments
* DNA rate as a percentage of all appointments within that mode



# Analysis 2 — Contribution to Monthly DNA Appointments

## Question

The second question looks at the problem from a different perspective:

**Of all DNA appointments occurring in a given month, what percentage came from each appointment mode?**

To calculate this, I first aggregated DNA appointments by month and appointment mode within a subquery.

I then used a **window aggregate function** to calculate the total number of DNA appointments within each month.



# What I Learned

One of the useful lessons from this exercise was the distinction between two apparently similar measures:

**DNA rate within an appointment mode**

> DNA appointments for that mode ÷ all appointments for that mode

versus:

**Share of monthly DNA appointments**

> DNA appointments for that mode ÷ all DNA appointments in that month

Although both are percentages, they answer different analytical questions.

The project also gave me my first practical opportunity to apply **window aggregate functions** to a healthcare dataset. I initially approached the problem using a subquery and plan to revisit the same analysis using a **Common Table Expression (CTE)** as I continue developing my SQL skills.

---

## Tools

* T-SQL
* Microsoft SQL Server / SQL environment
* NHS Open Data

---
## Next Steps

I plan to extend the project by exploring:

Rewriting the analysis using CTEs
Comparing DNA trends between GP practices
Parameterising GP practice selection


*This repository is a learning and portfolio project developed from work completed during the T-SQL Mastery Bootcamp.*
---
