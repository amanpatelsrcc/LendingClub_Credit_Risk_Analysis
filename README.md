# LendingClub_Credit_Risk_Analysis

#Problem Statement

LendingClub is a peer to peer lending platform that issues personal loans and grades them by risk (A to G). This project looks at their actual loan data from 2007 to 2018 to understand what drives default, whether their own risk grading actually holds up against real outcomes, and how the borrower base breaks down by income, credit history, and employment.

#Data

LendingClub was a real, publicly traded peer to peer lending company based in the US, operating from 2007 until it wound down its retail platform in 2020. This dataset is their actual historical loan book, not synthetic or simulated data.

Source: LendingClub Loan Data (Kaggle), accepted_2007_to_2018Q4.csv About 2.2 million rows and 151 columns in the raw file, narrowed down to about 27 relevant ones covering loan terms, borrower financials, credit history, and loan status.

#Tools Used
Python (Pandas) for cleaning, handling nulls, and mapping categorical fields to numeric
Power BI for the dashboard, DAX measures, and visualizations

#Methodology
Cleaned the raw dataset, dropped rows with minimal missing values, imputed employment length and mortgage account count with median values
Built a 3 page Power BI dashboard: Overview, Risk Analysis, and Segmentation
Default rate is calculated only on closed loans (Fully Paid or Charged Off), excluding loans still in progress like Current or Late, so the rate reflects actual resolved outcomes rather than being skewed by recent, unmatured loans

#Key Outcomes

#Overview
Total loans issued: 2,255.83K, totaling $33,948M
Overall default rate: 19.98%
Loan volume stayed flat until around 2012, then grew sharply through 2018, going from a few thousand loans a year to nearly 500K
About 47.7% of loans are in good standing, 40.4% are still unresolved, and 11.9% are bad

#Risk Analysis
Default rate climbs steadily from Grade A (6.04%) to Grade G (49.72%), confirming LendingClub's own grading system lines up with real default outcomes
FICO score and DTI both move in the expected direction too. Below 650 FICO defaults at 27.5% versus 8.88% for 750+, and DTI over 30% defaults at 29.17% versus 14.91% for under 10%
Education and wedding loans default less than other purposes even at lower grades, suggesting loan purpose carries some risk signal on its own, separate from grade

#Customer Segmentation
Borrowers earning 40K to 70K account for the highest loan volume, both in count and total amount, making them the core borrower base
Higher income borrowers take fewer loans but larger ones, a smaller but higher value segment
Default rate drops steadily as mortgage account count goes up, from 23.6% for borrowers with none down to 12.5% for those with 10 or more, likely tied to greater financial stability
Rented homes have the highest default rate at 23.23%, mortgaged homes the lowest at 17.22%

#Files
LendingClub_DataCleaning.ipynb – data cleaning notebook
LendingClub_Dashboard.pdf – exported dashboard pages
LendingClub_Dashboard.pbit – full interactive dashboard
