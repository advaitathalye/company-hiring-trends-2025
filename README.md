# Company-hiring-trends-2025
**Project Overview**

Job searching is often a guessing game. Where are the best opportunities, who’s hiring, and when should you apply?
This project leverages real job posting data scraped from LinkedIn to answer these questions with clarity and action.
With a relentless, problem-solving mindset, I built a Power BI dashboard that reveals who’s hiring, where, and when, all in one interactive view.

**Source:**

Public LinkedIn job postings (scraped, cleaned, and anonymized)
See Datajobs.csv for raw data

**Fields included:**
* Title: Job title (e.g., "Data Analyst")
* Company: Hiring company name
* Location: City/country
* Description: Full job description text
* Job Type: Remote, Hybrid, or Onsite (if available)

**Assumptions:**
* Each row = one job posting
* Job IDs are unique
* Locations/countries standardized
* Dataset covers a wide range of industries and company sizes

**Objectives & Business Problem**
* Who’s hiring the most for data roles in 2025?
* Which locations are hot spots for hiring?
* How do job posting trends change over time?
* What companies, locations, and months should jobseekers target?

This dashboard is built to empower jobseekers, recruiters, and analysts with data-driven insights, not guesswork.

**Available Visuals**
![Company Hiring Trends Dashboard](Company%20hiring%20trends.png)
* KPI Cards: Total jobs posted, unique companies, unique locations, most active company
* Bar Chart: Top hiring companies
* Pie Chart: Share of job postings by company
* Line Chart: Hiring trends over time (by company, month)
* Matrix Table: Job posting analysis by company, month, and location
* Slicers: Filter by company, year, month, or location for custom exploration

**Key DAX Explained**
Why DAX?
DAX (Data Analysis Expressions) powers custom calculations in Power BI, enabling deep insight beyond built-in aggregations.

**Total Unique Companies**
Total Unique Companies = DISTINCTCOUNT(Datajobs[Company])
Counts the number of unique companies posting jobs.

**Most Active Company**
Most Active Company =
  CALCULATE(
    VALUES(Datajobs[Company]),
    TOPN(
      1,
      VALUES(Datajobs[Company]),
      CALCULATE(COUNT(Datajobs[ID])),
      DESC
    )
  )
Finds the company with the highest number of postings.

**Total Unique Locations**
Total Unique Locations = DISTINCTCOUNT(Datajobs[Location])
Counts unique locations to show market breadth.

**Jobs Posted Over Time**
Uses COUNT(Datajobs[ID]) grouped by month/year to show hiring trends.

**How to Use**
Clone or download this repo.

Open Company Hiring Trends 2025.pbix in Power BI Desktop.

**Explore the dashboard:**

* Use slicers to filter by company, year, month, or location
* Hover on visuals for tooltips and more detail
* Drill into the matrix for company/month/location breakdowns
* Reference the DAX code above for any custom measure logic.

**Who Can Use This Project?**
Jobseekers: Identify target companies, locations, and the best time to apply
Recruiters: Benchmark your hiring against market trends
Data analysts: Learn Power BI dashboarding, DAX, and real-world data cleaning
Developers: Use the dataset for NLP, skill extraction, or AI-powered job tools



**References**
* Dataset inspired by LinkedIn job postings
* Dashboard built with Power BI
* Sample report structure inspired by Microsoft Power BI Desktop Samples

**Questions or suggestions? Open an issue or connect with me on LinkedIn.**
[Link Text](https:https://www.linkedin.com/in/advaitathalye/)
