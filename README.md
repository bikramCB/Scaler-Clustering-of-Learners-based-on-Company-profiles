# Scaler:Clustering of Learners based on Company profiles

## Problem Statement:
Scaler is an online tech-versity offering intensive computer science & Data Science courses through live classes 
delivered by tech leaders and subject matter experts. The meticulously structured program enhances the skills of 
software professionals by offering a modern curriculum with exposure to the latest technologies. It is a product by 
InterviewBit.
You are working as a data scientist with the analytics vertical of Scaler, focused on profiling the best companies 
and job positions to work for from the Scaler database. You are provided with the information for a segment of 
learners and tasked to cluster them on the basis of their job profile, company and other features. Ideally, these 
clusters should have similar characteristics.

## Data:
1. Unnamed 0’- Index of the dataset
2. Email_hash- Anonymised Personal Identifiable Information (PII)
3. Company_hash - This represents an anonymized identifier for the company, which is the current employer of the learner.
4. orgyear- Employment start date
5. CTC- Current CTC
6. Job_position- Job profile in the company
7. CTC_updated_year: Year in which CTC got updated (Yearly increments, Promotions)

## Tech used:
K-Means Clustering

## Tools Used:
Numpy, Pandas , Sklearn

## Challenges:
Alomost 2 lakh learners data were collected from Scaler data base by providing google form.
1. While cleaning the datasets company and job position are having different types of characters so it will take longer time to fix it in a proper way. Because all these info were collected in google form so 
   manual errors were there.
2. some ctc updated year misstakenly put year be fore joining so fix it with org joining year.

## Feature Engineering:
1. fill  null rows of company , job position with 'others' since these two columns are very essentials for profiling.
2. Then remove duplicate rows.
3. Fill Org joining year coulmn null values with median value respect to company joining year.
4. Remove outlier from org joining year,ctc column using Clip method 99.5 % data remaing for model building.
5. create a new feature 'year of experience' by substracting 2024 - org year.
6. create column 'designation' by manual clustering company, job position, YOE if ctc 50 percentile < 3 , 50 to 75 percentile 2 and above 75 1  : designation
7. create column 'Class' by manual clustering company, job position if ctc 50 percentile < 3 , 50 to 75 percentile 2 and above 75 1  : Class
8.  create column 'Tier' by manual clustering company if ctc 50 percentile < 3 , 50 to 75 percentile 2 and above 75 1  : Tier

## Solutions:
1. Now consider a df having 'ctc, 'YOE', 'class', 'designation', 'tier' and apply Kmeans clustering algo K= 3 according to dendogram.
2. Now filter out every cluster and find mean, median and mode and did EDA of every cluster.
3. And then profiling the cluster based on tier , designation and class respectively.




