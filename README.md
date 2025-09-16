Project Overview
This project is a Power BI dashboard built to analyze Jira issue data. The goal is to provide clear insights into project management and team performance by tracking:

1.Issue trends (Created, Resolved, Unresolved)
2.Cycle time and story points analysis
3.Team workload distribution by assignee
4.Issue breakdown by priority, type, and status

Tools & Technologies

1.Power BI Desktop – Data visualization & dashboarding
2.Excel/CSV (Synthetic Jira Data) – Dataset with 200 Jira-style issue records
3.Power Query – Data cleaning & transformation
4.DAX – Custom measures for KPIs

Dataset Details

The dataset includes fields like:
1.IssueKey
2.Project
3.IssueType
4.Summary
5.Priority
6.Status
7.Assignee
8.CreatedDate, ResolvedDate
9.StoryPoints
9.CycleTime

Key Dashboard FeatureS
KPI Cards

1.Total Issues
2.Resolved Issues
3.Unresolved Issues
4.Total Story Points
5.Average Cycle Time

Visuals
1.Issue Status Breakdown → Bar chart showing issues by status
2.Issues per Assignee → Table showing workload distribution
3.Issues by Type → Pie chart (Bug, Task, Story, Epic, etc.)
4.Assignee by Status & Priority → Clustered bar chart
5.Story Points vs Cycle Time → Scatter plot to analyze efficiency
6.Issues by Priority → Donut chart
7.Issues by Completed Date → Line chart showing trends

---Data Preparation & Cleaning---
Steps taken in Power Query:
1.Removed duplicate Issue IDs
2.Fixed typos and standardized column values (e.g., Priority, Status)
3.Converted columns to correct data types (Dates, Whole Numbers, Text)
4.Filled missing values (Story Points, Cycle Time) with default or average values
5.Created calculated columns for Cycle Time = ResolvedDate – CreatedDate

DAX Measures Created
1.Total_Issues = COUNTROWS(Jira)
2.Resolved_Issues = CALCULATE(COUNT(Jira[IssueKey]), NOT(ISBLANK(Jira[ResolvedDate])))
3.Unresolved_Issues = [Total_Issues] - [Resolved_Issues]
4.Total_Story_Points = SUM(Jira[StoryPoints])
5.Avg_Cycle_Time = AVERAGE(Jira[CycleTime])

Steps to Reproduce the Dashboard

1.Load Data
2.Import Dataset into Power BI
3.Transform Data
4.Clean and format columns in Power Query
5.Create Relationships

---Insights----
From the sample dataset:

1.57 Total Issues tracked
2.35 Resolved, 22 Unresolved
3.Most issues are of Medium priority
4.Story Points and Cycle Time show correlation for higher workloads
5.Assignee workload is fairly balanced across team members


