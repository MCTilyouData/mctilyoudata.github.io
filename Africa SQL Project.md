# **Africa and the World Bank: Analyzing Support from the IDA**

The **International Development Association (IDA)** is a branch of the World Bank Group and 
is headquarted in Washington, D.C. in the United States. The branch was created in 1960 and aims at providing 
concessional loans and grants to the world's poorest developing countries to help **end extreme
poverty** and **promote shared prosperity**. IDA is funded largely by contributions from the governments
of its member countries. To date, thirty-six countries have graduated, and many of them have become IDA donors themselves. 
These countries include China, Chile, India, South Korea, and Turkey. 

**Africa** has received the most support from the IDA, taking in around **75% of the total IDA commitments**, disbursed to the 39 poorest countries on the continent. To see where the IDA's loans and grants were disbursed and how the money was being used, the data
was displayed and analyzed in SQL.

## **Objective**
Using SQL, my goal was to accomplish the following objectives:
1. Determine the total amount of money disbursed to Africa, and **which region of Africa was receiving the most**.
2. Focusing on the region that received the most, I wanted to determine the amount of money they had paid back to the IDA and the amount of debt the IDA had cancelled for that region, as well as the amount of money the region still owes to the IDA.
3. Analyze **what projects** the majority of the money was being used for in that particular region.

## **Key Findings**
1. The countries within Africa have received a total of 5005 loans and grants from the IDA, totaling over $82.1 Billion.
2. The **Region labeled Africa** received the most with a total of 2891 loans/grants, totaling over $36.3 Billion.
3. Over **$200 Million of that debt has been cancelled** for the region of Africa.
4. The region of Africa has **repaid over $97 Million** to the IDA, but still **owes over $1.1 Billion**.
5. Top projects in this region include "Niger Basin Water Resources", "Regional HIV/AIDS Treatment Project", and the "Regional Trade Facilitation Project".

## **The Data**
The data for this project was taken directly from the World Bank Group's financial website. The data is updated regulary and can be found [here](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx/about_data). It was downloaded and imported into a program called [CSVfiddle.io](https://csvfiddle.io/#JTdCJTIyaXNUYWJsZU1ldGFkYXRhT3BlbiUyMiUzQWZhbHNlJTJDJTIyaXNOZXdUYWJsZUZvcm1PcGVuJTIyJTNBZmFsc2UlMkMlMjJpc0NvbmZpcm1EZWxldGVRdWVyeU9wZW4lMjIlM0FmYWxzZSUyQyUyMmlzQ29uZmlybURyb3BUYWJsZU9wZW4lMjIlM0FmYWxzZSUyQyUyMmlzU2hhcmVEaWFsb2dPcGVuJTIyJTNBZmFsc2UlMkMlMjJkYlJlYWR5JTIyJTNBZmFsc2UlMkMlMjJ0YWJsZXMlMjIlM0ElNUIlNUQlMkMlMjJxdWVyaWVzJTIyJTNBJTdCJTIyMCUyMiUzQSU3QiUyMmlkJTIyJTNBMCUyQyUyMnRpdGxlJTIyJTNBJTIyVW50aXRsZWQlMjBxdWVyeSUyMiUyQyUyMmJvZHklMjIlM0ElMjIlMjIlMkMlMjJyZXN1bHQlMjIlM0ElNUIlNUQlMkMlMjJlcnJvciUyMiUzQW51bGwlN0QlN0QlMkMlMjJhY3RpdmVRdWVyeUlkJTIyJTNBMCUyQyUyMmFjdGl2ZVRhYmxlTWV0YWRhdGFDb2x1bW5zJTIyJTNBJTVCJTVEJTJDJTIybG9jYWxUYWJsZXNUb1dhcm4lMjIlM0ElNUIlNUQlMkMlMjJpc1F1ZXJ5SW5Qcm9ncmVzcyUyMiUzQWZhbHNlJTJDJTIyZGlkQWRkTmV3VGFibGVTdWNjZWVkJTIyJTNBbnVsbCUyQyUyMmFkZE5ld1RhYmxlRXJyb3IlMjIlM0FudWxsJTdE), which mimics SQL's capabilities, without having to download SQL to your desktop. The data file was named "banking_data" and is used in the queries stated in the project below to analyze the 30 columns and 1.25 million rows contained within the set. Each row in this data set represented a disbursement from the IDA, and listed things like the disbursement date, region, country, amount disbursed, percent charge rate, amount repaid, amount cancelled, and amount owed to the IDA. You can see the total data set below. 

<img src ="images/Data Dictionary - IDA Bank Project.png?raw=true"/>

## **SQL Commands Used in This Project:**
Aggregate Functions:
SUM | AVG | MAX | MIN | COUNT

Operators:
AND | NOT | OR | NULL | LIKE | DESC

Clauses:
WHERE | GROUP BY | ORDER BY | LIMIT | AS

## **Analysis: Overview**
I began by gathering some basic information on the data. I collected all of the columns and a portion of the rows using a LIMIT function to get a feel for the data. The IDA has distributed over $55 Trillion to countries in need since the branch was developed. After some research into the IDA, I knew that Africa in general had received a large portion of the IDA's money and wanted to investigate the allocation of funds further. Take note that the data set splits Africa up into 4 different regions: **Africa, Eastern and Southern Africa, Middle East and North Africa, and Western and Central Africa**. I used a COUNT function, as well as a SUM function, to determine that the **region labeled Africa** has received the greatest amount of loans and grants, and the highest total amount of funds. I decided to focus on this region for my analysis. For the rest of this project, the **region labeled Africa will simply be referred to as Africa**. The query below shows the filter used to separate the data and focus on disbursements to Africa.

<img src ="images/SQL Filter Africa.png?raw=true"/>

The COUNT function mentioned earlier revealed that there were a total of 2,891 loans and/or grants disbursed to Africa since the start of the IDA.

## **Analysis: Money Distrubted to Africa**
Using a simple SUM function, I was able to find that over $36 billion has been distributed to Africa over the past 63 years. This query is shown below. Using an AVG function, it was determined that the average loan/grant amount was around $12.5 million. 
<img src ="images/Total Africa Loans.png?raw=true"/>
<img src ="images/Total Africa Loans Amount.png?raw=true"/>

## **Analysis: Money Repaid**
Continuing to look into Africa's data, I found that Africa has paid back over $97 million to the IDA, but still owes a whopping $1.1 billion. Luckily, out of the $36 billion that Africa has received over the years, the IDA has forgiven or cancelled nearly $235 million of that. Using a MAX function, it was noted that the largest cancelled loan totaled over $2.6 million. 



