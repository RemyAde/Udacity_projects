# Effect of Prosper Loan Characteristics on Loan Outcome
## by Samuel Aderemi


## ProsperLoans Dataset

> The Dataset I used for this visualization project is the ProsperLoans dataset. It comprises of 81 columns and over 113,000 records.
It contains information about each loan listed with Prosper dating since 2005 to 2015. Some of the information it holds are _borrower's rate, listing category, term of loan, loan status, and many more_. I will focus on exploring and visualizing the attributes of the different loan statutes enlisted. A copy of the dataset can be gotten from [here](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv) and the link to its' documentation [here](https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&source=editors&ust=1660601480353771&usg=AOvVaw0qGzdR69H3usl9dHb8gJcC)


## Summary of Findings

From the exploration conducted, I discovered that there was a very strong relationship between borrower's rate and and the rating systems (CreditGrade & ProsperRating). I observed that the relationship is linear in nature, with lower borrower's
rate correlating with lower risk investments while higher borrower's rate correlate with with higher risk investments. I also found out that borrower's rate was a major determinant of loan status. There also existed a linear between borrower's rate and loan status, lower rates correlate with successful and those with similar potentiial while higher rates correlate with defaulted payments. 

Aside the main features, I focused on the categories of people who apply for Prosper loans. I discovered that most loan borrowers are people of the working class, and their major reason for borrowing of loans are for debt consolidations, business is fifth on their list. Overall Prosper has most of it's loans paid or in the process of being paid.

## Key Insights for Presentation

> For this presentation I focus on the effect borrower rate has on the outome of the loan. I first explore the monthly income for each listing which I performed a logarithmic transform then plotted the resulting distribution

> To proceed, I then introduced the borrower rate to the categorical variables one by one. I started off with the Loan Status to see the variation using a barplot, followed by Prosper Rating. I plotted a final multivariate plot of Loan Status, Credit Grade and the Mean Borrower Rate. I made sure to use suitable categorical color encoding. 