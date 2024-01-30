# **Africa and the World Bank: Analyzing Support from the IDA**

The **International Development Association (IDA)** is a branch of the World Bank Group and 
is headquarted in Washington, D.C. in the United States. The branch was created in 1960 and aims at providing 
concessional loans and grants to the world's poorest developing countries to help end extreme
poverty and promote shared prosperity. IDA is funded largely by contributions from the governments
of its member countries. To date, thirty-six countries have graduated, and many of them have become IDA donors themselves. 
These countries include China, Chile, India, South Korea, and Turkey. 

In recent years, the African region has received 75% of the total IDA commitments, with the country of Africa
receiving the most. To see where the IDA's commitments were disbursed and how the money was being used, the data
was displayed and analyzed in SQL.

## **Objective**
Using SQL, my goal was to accomplish the following objectives:
1. Determine the total amount of money disbursed to Africa.
2. Determine the amount of money Africa has paid back to the IDA and the amount of debt the IDA has cancelled for Africa.
3. Determine the amount of money Africa still owes to the IDA.
4. Analyze what projects the majority of the money was being used for in Africa.

## **Key Findings**
1. The country of Africa has received a total of 2891 loans and grants from the IDA, totaling over $36.3 Billion.
2. Over $200 Million of that debt has been cancelled for Africa.
3. Africa has repaid over $97 Million to the IDA, but still owes over $1.1 Billion.
4. Top projects include "Niger Basin Water Resources", "Regional HIV/AIDS Treatment Project", and the "Regional Trade Facilitation Project".

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
I began by gathering some basic information on the data. I collected all of the columns and a portion of the rows using a LIMIT function to get a feel for the data. After some research into the IDA, I knew that Africa had received a large portion of the IDA's money and wanted to investigate the country further. I used the query below to filter the data to focus on disbursements to Africa.

<img src ="images/SQL Filter Africa.png?raw=true"/>

I then used a COUNT function to determine that there were a total of 2,891 loans and/or grants disbursed to Africa since the start of the IDA.

## **Analysis: Money Distrubted to Africa**
Using a simple SUM function, I was able to find that over $36 Billion has been distributed to the African region, with an average loan/grant amount of $12.5 million. 




