# social-listening-sql-analysis
Social listening analysis using SQL and Python to extract and analyse COVID-19-related public discourse and sentiment from Twitter data.

## Overview
This project analyses social media (i.e., Twitter) discourse around COVID-19 using SQL and Python. The goal is to simulate social listening workflows by applying keyword-based filtering, Boolean query logic, and sentiment analysis to identify trends in public conversations.

## Dataset
COVID-19 Twitter Dataset (Apr–Jun 2020)

## Tools Used
- Python (pandas, sqlite3)
- SQL (SQLite)

## Methodology

### 1. Data Preparation
- Loaded CSV dataset into a SQLite database
- Structured data into a table for querying

### 2. Keyword-Based Filtering
Used SQL `LIKE` conditions to extract relevant discourse:
- Vaccine-related: `%vacc%`
- Lockdown-related: `%lockdown%`
- Government-related: `%government%`, `%president%`, `%minister%`, `%state%`, `%authority%`

### 3. Boolean Query Design
Combined multiple keywords using OR conditions to better capture real-world discourse patterns.

### 4. Sentiment Analysis
Analysed sentiment distribution (positive, neutral, negative) across filtered topics.

## Key Findings

### 1. Government discourse dominates
Government-related discussions (5308 mentions) were the most prominent, exceeding both lockdown (3214 mentions) and vaccine (2198 mentions) topics. This suggests that public discourse was strongly centred on political leadership and institutional responses.

### 2. Importance of Boolean query design
Initial keyword searches significantly underestimated government-related discourse. Expanding keyword sets revealed a much broader conversation, highlighting the importance of robust query construction in social listening.

### 3. Sentiment trends in vaccine discourse
Vaccine-related tweets were mostly neutral (53%), followed by positive (30%) and negative (17%) sentiment. This indicates that while discussions were largely informational, public attitudes leaned more positive than negative.

## Example SQL Query

```sql
SELECT sentiment, COUNT(*) AS count
FROM tweets
WHERE clean_tweet LIKE '%vacc%'
GROUP BY sentiment;
