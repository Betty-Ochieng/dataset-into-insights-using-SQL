# dataset-into-insights-using-SQL
## Social Media Usage Dataset Analysis

**Dataset Details:**
- Number of Records: 100
- Columns: UserID, Platform, TimeSpentMinutes, ...

**Difficulties Encountered:**
- Needed to handle missing values in the 'TimeSpentMinutes' column.
- Data format required conversion for accurate analysis.

**Interesting Insight:**
- Discovered that users spend significantly more time on Platform X compared to others.
  Ask Away (30 pts):

**Formulate 2 questions about the data (e.g., what are popular shows in different countries?).**
-Question 1: How does the average time spent on social media vary between different age groups?

This question aims to explore if there are significant differences in social media usage habits across various age demographics.
-Question 2: Is there a correlation between the time spent on social media and the day of the week?

This question seeks to understand if users spend different amounts of time on social media depending on whether it's a weekday or weekend.
**Write basic SQL queries (WHERE, ORDER BY) to find answers.**
-- Query for Question 1: Average Time Spent on Social Media by Age Group
SELECT 
    CASE
        WHEN Age >= 18 AND Age <= 24 THEN '18-24'
        WHEN Age >= 25 AND Age <= 34 THEN '25-34'
        WHEN Age >= 35 AND Age <= 44 THEN '35-44'
        ELSE 'Other'
    END AS AgeGroup,
    AVG(TimeSpentMinutes) AS AvgTimeSpent
FROM 
    SocialMediaUsage
GROUP BY 
    AgeGroup
ORDER BY 
    AvgTimeSpent DESC;
-Explanation:
The CASE statement categorizes users into age groups (18-24, 25-34, 35-44, and Others).
AVG(TimeSpentMinutes) calculates the average time spent on social media for each age group.
GROUP BY AgeGroup groups the results by the defined age groups.
ORDER BY AvgTimeSpent DESC sorts the results in descending order of average time spent, showing which age group spends the most time on social media.
-- Query for Question 2: Correlation Between Time Spent and Day of the Week
SELECT 
    DAYNAME(InteractionDate) AS DayOfWeek,
    AVG(TimeSpentMinutes) AS AvgTimeSpent
FROM 
    SocialMediaUsage
GROUP BY 
    DayOfWeek
ORDER BY 
    DAYOFWEEK(InteractionDate);
-Explanation:
DAYNAME(InteractionDate) extracts the name of the day from the InteractionDate column.
AVG(TimeSpentMinutes) calculates the average time spent on social media for each day of the week.
GROUP BY DayOfWeek groups the results by the day of the week.
ORDER BY DAYOFWEEK(InteractionDate) orders the results by the day of the week starting from Sunday (DAYOFWEEK function returns 1 for Sunday, 2 for Monday, etc.).
**Share what you learned from the answers.**
-The insights gleaned from these SQL queries provide valuable information about user behavior and engagement patterns on social media platforms. By leveraging these findings, businesses and advertisers can optimize their strategies to better connect with their target demographics and improve overall engagement metrics. This analysis underscores the importance of data-driven decision-making in digital marketing and audience engagement strategies.
**Presentation Power (20 pts):**

---

### Slide 1: Introduction

**Title Slide**
- **Title:** Analyzing Social Media Usage Patterns
- **Subtitle:** Insights from Average Time Spent By User on Social Media

---

### Slide 2: Dataset Overview

**Introduction to the Dataset**
- **Dataset Name:** Average Time Spent By User on Social Media
- **Source:** The dataset was sourced from dataset1. It includes data on user demographics, social media platforms, and the average time spent by users on each platform.
- **Goals:** Our goal is to uncover patterns in social media usage across different demographics and platforms to inform targeted marketing strategies.

---

### Slide 3: Import Process

**Importing the Dataset**
- **Tool Used:** MySQL Workbench
- **Steps:**
  - Created a new database `SocialMediaDB`.
  - Imported dataset into `SocialMediaUsage` table.
- **Challenges:** Addressed data formatting issues and missing values in platform information to ensure data integrity and accuracy.

---

### Slide 4: Interesting Finding

**Key Insight**
- **Insight:** Users aged 18-24 spend significantly more time on social media compared to other age groups.
- **Significance:** This demographic represents a critical segment for advertisers and marketers aiming to reach a highly engaged audience on social media platforms.

---

### Slide 5: Cool Facts

**Two Cool Facts**
1. **Fact 1:** Monday shows the highest average time spent on social media among weekdays, suggesting increased usage at the start of the week.
2. **Fact 2:** Instagram demonstrates the highest average time spent compared to other social media platforms, indicating strong user engagement and potential advertising opportunities.

---

### Slide 6: Questions Explored

**Formulated Questions**
- **Question 1:** How does average time spent vary between different age groups?
- **Question 2:** Is there a correlation between time spent and the day of the week?

---

### Slide 7: SQL Queries and Insights

**SQL Queries and Learnings**
- **Query 1: Average Time Spent by Age Group**
  ```sql
  SELECT 
      CASE
          WHEN Age >= 18 AND Age <= 24 THEN '18-24'
          WHEN Age >= 25 AND Age <= 34 THEN '25-34'
          WHEN Age >= 35 AND Age <= 44 THEN '35-44'
          ELSE 'Other'
      END AS AgeGroup,
      AVG(TimeSpentMinutes) AS AvgTimeSpent
  FROM 
      SocialMediaUsage
  GROUP BY 
      AgeGroup
  ORDER BY 
      AvgTimeSpent DESC;
  ```
  - **Insight:** The 18-24 age group spends the most time on social media, followed by the 25-34 age group, indicating varying levels of engagement across different demographics.

- **Query 2: Time Spent by Day of the Week**
  ```sql
  SELECT 
      DAYNAME(InteractionDate) AS DayOfWeek,
      AVG(TimeSpentMinutes) AS AvgTimeSpent
  FROM 
      SocialMediaUsage
  GROUP BY 
      DayOfWeek
  ORDER BY 
      DAYOFWEEK(InteractionDate);
  ```
  - **Insight:** Weekdays (especially Mondays and Thursdays) see higher average time spent on social media compared to weekends, suggesting different usage patterns based on weekdays and weekends.

---

### Slide 8: Charts and Visualizations

**Visualization of Findings**
- **Chart 1: Average Time Spent per Social Media Platform**
  - Bar chart illustrating average time spent on each social media platform, highlighting Instagram as the platform with the highest engagement.
  
- **Chart 2: Time Spent Variation by Day of the Week**
  - Line chart showing the variation in average time spent on social media across different days of the week, emphasizing peak usage on weekdays.

- **Chart 3: Age Group Distribution of Time Spent**
  - Pie chart depicting the distribution of average time spent on social media among different age groups, with a focus on the 18-24 age group.

---

### Slide 9: Summary

**Project Summary**
- **Achievements:** Identified key demographic trends and behavioral patterns in social media usage.
- **Impact:** Insights can inform targeted marketing strategies, content scheduling, and platform-specific advertising campaigns.
- **Future Steps:** Further exploration into user interactions, content preferences, and real-time engagement metrics to enhance marketing effectiveness.

---

### Slide 10: Q&A

**Questions and Discussion**
- any questions?

---

### Closing Remarks

**Thank You!**
- **Contact Information:** ochieng2506@gmail.com

---
