# Financial Recruitment & Salary Intelligence Dashboard

## Project Overview

This project focuses on analysing recruitment and salary-related data to understand job market trends, salary distributions, company ratings, and recruitment performance.

Using Power BI, I developed a three-page interactive dashboard to explore job postings, applicant trends, salary expectations, and hiring outcomes. The analysis provides insights into recruitment activities and helps highlight patterns that can support better workforce and hiring decisions.

## Project Objectives

The main objectives of this project were to:

- Analyse the total number of job postings and applicants.
- Examine salary distributions, including minimum, maximum, and average salary figures.
- Compare open and closed job postings.
- Evaluate company and recruiter ratings.
- Assess recruitment performance using interviews, hired candidates, and hiring success rate.
- Explore experience requirements across job postings.

## Tools Used

- **Microsoft Excel:** Dataset storage and initial inspection.
- **Power BI:** Data modelling, DAX calculations, interactive visualisations, and dashboard development.

## Dashboard Structure

The report consists of three pages:

1. **Recruitment Overview:** Analysis of job postings, companies, applicants, and hiring status.
2. **Salary Intelligence:** Analysis of salary ranges, salary expectations, skills, and qualifications.
3. **Recruitment Performance:** Analysis of interviews, hired candidates, and hiring success.

## Data Preparation

Before developing the dashboard, I used Power Query in Power BI to prepare the dataset for analysis.

The data preparation process involved:
- Inspecting the dataset for inconsistencies.
- Cleaning and transforming the data.
- Preparing the columns for analysis and visualisation.
- Ensuring the dataset was suitable for creating DAX measures and dashboard visuals.

## DAX Measures and Calculations

The project includes 16 DAX measures grouped into four categories:

1. Recruitment Overview
2. Salary Analysis
3. Company and Recruiter Ratings
4. Hiring Performance

These measures include calculations for total job postings, total applicants, average salary, salary ranges, open-to-closed ratio, company ratings, recruiter ratings, total interviews, total hired candidates, and hiring success rate.

**The complete DAX formulas and explanations are documented below this section.**

## DAX Measures and Calculations

A total of 16 DAX measures were developed to analyse recruitment activities, salary trends, company ratings, and hiring performance.

### 1. Recruitment Overview

**1. Total Job Postings**

```DAX
Total Job Postings = COUNTA('Finance Dataset'[Job Title])
```
Counts the total number of job postings in the dataset.

**2. Total Applicants**

```DAX
Total Applicants = SUM('Finance Dataset'[Applicants Count])
```
Calculates the total number of applicants across all job postings.

**3. Applicants to Job**

```DAX
Applicants to Job = DIVIDE(SUM('Finance Dataset'[Applicants Count]),COUNTROWS('Finance Dataset'),0)
```
Calculates the average number of applicants per job posting.

**4. Av. Application**

```DAX
Av.Application = AVERAGE('Finance Dataset'[Applicants Count])
```
Calculates the average number of applicants received per job posting.

**5. Open-to-Closed Ratio**

```DAX
Closed vs Ratio = DIVIDE(COUNTROWS(FILTER('Finance Dataset','Finance Dataset'[Hiring Status]="open")),COUNTROWS(FILTER('Finance Dataset','Finance Dataset'[Hiring Status] IN {"closed"})),0)
```
Compares the number of open job postings with the number of closed job postings.

### 2. Salary Analysis

**6. Average Salary**

```DAX
Average Salary = AVERAGE('Finance Dataset'[Salary midpoint])
```
Calculates the average salary midpoint across all job postings.

**7. Average Minimum Salary**

```DAX
Av.Salary Min = AVERAGE('Finance Dataset'[Salary Min])
```
Calculates the average minimum salary offered across job postings.

**8. Average Maximum Salary**

```DAX
Av.Salary Max = AVERAGE('Finance Dataset'[Salary Max])
```
Calculates the average maximum salary offered across job postings.

**9. Average Salary Range**

```DAX
Av. Salary Range = AVERAGEX('Finance Dataset','Finance Dataset'[Salary Max]-'Finance Dataset'[Salary Min])
```
Calculates the average difference between the maximum and minimum salary offered per job posting.

### 3. Company and Recruiter Ratings

**10. Average Company Rating**

```DAX
Av. Company Rating = AVERAGE('Finance Dataset'[Company Rating])
```
Calculates the average rating of companies represented in the dataset.

**11. Average Recruiter Rating**

```DAX
Av. Recruiter Rating = AVERAGE('Finance Dataset'[Recruiter Rating])
```
Calculates the average rating of recruiters across the job postings.

### 4. Hiring Performance

**12. Total Hired Candidates**

```DAX
Total Hired Candidate = SUM('Finance Dataset'[Hired Candidates])
```
Calculates the total number of candidates hired.

**13. Total Interviews**

```DAX
Total Interview = SUM('Finance Dataset'[Interview Count])
```
Calculates the total number of interviews conducted.

**14. Hiring Success Rate**

```DAX
Hiring Success Rate = DIVIDE(SUM('Finance Dataset'[Hired Candidates]), SUM('Finance Dataset'[Applicants Count]),0)
```
Measures the proportion of applicants who were successfully hired.

**15. Total Hiring Companies**

```DAX
Total Hiring Companies = DISTINCTCOUNT('Finance Dataset'[Company Name])
```
Counts the number of unique companies represented in the dataset.

**16. Average Experience Requirement**

```DAX
Av. experience requirement = AVERAGE('Finance Dataset'[Years of Experience])
```
Calculates the average years of experience required across job postings.

## Key Insights and Findings

The analysis of the finance recruitment dataset revealed several patterns relating to job demand, salary expectations, required skills, and recruitment performance.

### 1. Finance Job Market Overview

**High competition for finance jobs**

The dashboard recorded 2.31K job postings and 468K applicants, representing approximately 203 applicants per job posting. This indicates intense competition among job seekers. The average experience requirement was 6.07 years, highlighting the importance employers place on practical work experience.

**Demand across finance job roles**

The most advertised positions were:
- Internal Auditor: 202
- Risk Analyst: 201
- FP&A Analyst: 191
- Investment Analyst: 190
- Financial Analyst: 170
- Treasury Analyst: 169

Internal Auditor and Risk Analyst positions recorded the highest number of job postings among the roles displayed.

**Departmental hiring activity**

Audit recorded the highest departmental hiring figure (324), followed by Corporate Finance (318), Accounting (280), Risk Management (275), Investment Banking (273), and Treasury (273).

**Work arrangements and employment types**

Work arrangements were relatively balanced:
- Onsite: 33.69%
- Hybrid: Approximately 33.3%
- Remote: 32.83%

Employment types also had similar distributions, with Full-time roles at 33.82%, Internships at approximately 33.3%, and Contract positions at 32.87%.

These findings indicate that finance opportunities are available across different work arrangements and employment types.

### 2. Salary and Skills Intelligence

**Salary distribution**

The average salary midpoint was approximately $77.03K, with an average minimum salary of $59.31K and an average maximum salary of $94.75K.

Among the displayed job titles, Tax Analyst recorded the highest average salary at approximately $78K, followed by Treasury Analyst at approximately $77K.

**Salary by experience level**

Executive-level positions recorded the highest average salary at approximately $79.3K. Junior roles followed at $77.7K, while Mid-Level, Entry-Level, and Senior positions recorded approximately $76.5K, $76.3K, and $75.7K respectively.

**In-demand technical skills**

The most frequently represented tools in the dataset were:
- Excel: 853
- Python: 841
- Power BI: 800
- SQL: 800

This highlights the relevance of data analysis and technical skills within the finance job market.

**Certification and recruiter ratings**

Approximately 81% of the job postings required certification, while the average recruiter rating was 3.99.

This suggests that professional certifications may be an important consideration for candidates pursuing finance-related opportunities.

### 3. Recruitment Performance and Efficiency

**Recruitment performance**

The dashboard recorded approximately 240K interviews and 13K hired candidates, with a hiring success rate of 2.70%. The average time to hire was 33 days.

**Hiring status distribution**

- Open: 790 (34.17%)
- Closed: 775 (33.52%)
- Filled: 747 (32.31%)

The distribution shows a relatively balanced number of open, closed, and filled job postings.

**Hiring across industries**

Manufacturing recorded the highest number of hired candidates (307), followed by Consulting (295), Banking (280), Investment (278), and Insurance (261).

**Salary by industry**

Consulting recorded the highest average salary at approximately $80K, followed by Investment at approximately $78K. Insurance, Manufacturing, and Banking recorded average salaries of approximately $77K, $76K, and $76K respectively.

**Recruiter performance**

The recruiter performance table showed differences in hiring success rates across individual recruiters, suggesting variations in recruitment outcomes.

### 4. Overall Key Findings

The analysis revealed four major findings:

1. **High employment competition:** The large applicant pool relative to job postings indicates that finance job seekers face considerable competition.
2. **Diverse recruitment demand:** Hiring activity spans several finance specializations, with Audit and Corporate Finance leading the departmental figures.
3. **Importance of technical and professional skills:** Excel, Python, Power BI, SQL, and professional certifications feature prominently in the dataset.
4. **Differences in recruitment outcomes and salaries:** Hiring activity and salary levels vary across industries, while recruiter performance also differs.

### 5. Business Recommendations

Based on the findings, the following recommendations can be considered:

1. **For job seekers:** Develop relevant skills in auditing, risk management, financial analysis, Excel, SQL, Python, and Power BI to improve competitiveness.
2. **For graduates and entry-level candidates:** Pursue internships, professional certifications, and practical experience to strengthen their employment prospects.
3. **For employers:** Improve recruitment processes to identify suitable candidates efficiently from the large applicant pool.
4. **For career development:** Pay attention to departments such as Audit, Corporate Finance, and Risk Management, which recorded relatively high hiring activity.

### Conclusion

This project provided insights into finance job market trends, salary expectations, required skills, and recruitment performance. The findings show that although finance opportunities exist across different specializations and employment arrangements, the high number of applicants relative to available postings makes the market competitive.

The analysis also highlights the importance of technical skills, professional experience, and certifications in improving employment prospects. The interactive Power BI dashboard makes these patterns easier to explore and supports data-driven interpretation of recruitment trends.

## Dashboard Screenshots

### 1. Finance Job Market Overview
![Finance Job Market Overview](page%201.PNG)

### 2. Salary & Skills Intelligence
![Salary & Skills Intelligence](page%202.PNG)

### 3. Recruitment Performance & Efficiency
![Recruitment Performance & Efficiency](page%203.PNG)
