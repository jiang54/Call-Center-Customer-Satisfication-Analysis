# Pwc Switzerland Power BI virtual case experience - Call Center Customer Satisfication Analysis
![image](https://user-images.githubusercontent.com/24377958/226614142-0032363b-ecec-4d73-bf2b-159a35db0ce7.png)

# Table of Contents

- [Problem Statement](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Problem-Statement)
- [Data Sourcing](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Data-Sourcing)
- [Data Preparation](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Data-Preparation)
- [Data Modeling](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Data-Modeling)
- [Data Analysis](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Data-Analysis)
- [Data Visualization](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Data-Visualization)
- [Insights](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Insights)
- [Virtual Case Experience Link](https://github.com/jiang54/-Diversity-and-Inclusion-Analysis#Virtual-Case-Experience-Link)


---
# Problem Statement

The purpose of this analysis is to create a dashboard for the call center manager that reflects all relevant Key Performance indicators(KPIs)
and metrics in the dataset.

Possible KPIs include(but not limited to):
- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agents performance quadrant -> average handle time(talk duration) vs calls answered


---

# Data Sourcing

The Dataset used for this analysis was presented by [Pwc Switzerland](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and available at:

- [Call Center Dataset](https://github.com/jiang54/Call-Center-Customer-Satisfication-Analysis/blob/main/01%20Call-Center-Dataset.xlsx)


---

# Data Preparation

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.

The call center dataset is given by a table named:

- `Call Center` which has `10 columns and 5000 rows` of observation


The tabulation below shows the `Call Center` table with its column names and their description:
| Column Name | Description |
| ----------- | ----------- |
| Call Id | Represents every unique observation in the dataset |
| Agent | Describes the name of the agent |
| Date | Describes the date of the call |
| Time | Represents the time of the call  |
| Topic | Describes the topic of the caller |
| Answered (Y/N) | Describes if the call was Answered or not |
| Resolved | Describes if the problem was Resolved or not |
| Speed of answer in seconds | Represents the speed of answer in seconds |
| AvgTalkDuration | Represents the average talk duration of call |
| Satisfaction rating | Represents the satisfaction rating of the agent during the call |

Data Cleaning for the dataset was done in power query as follows:

- Rows with missing values may carry important information and should not be indiscriminately removed
- Each of the columns in the table were validated to have the correct data type 



---

# Data Modeling

After the dataset was cleaned and transformed, it was ready to be modeled.
The fact and dimension have been combined into one table and is shown in the data model below

![image](https://user-images.githubusercontent.com/24377958/226616203-ea251e2b-dc9f-4e6f-a0ac-a9fe9ffa7afe.png)

# Data Analysis
Add Necessary Measures and tables
New table `Satisfy = 
FILTER(
    VALUES(Sheet1[Satisfy]),
    NOT(ISBLANK(Sheet1[Satisfy]))
)`
