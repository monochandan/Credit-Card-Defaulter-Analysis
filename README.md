# Credit-Card-Defaulter-Analysis
- Power BI
- DAX
- EXCEL Worksheet

# Credit Card Defaulter Analysis Dashbord



we have a credit card dataset. This is going to lay the foundation or give an idea of what kind of data one can expect when comes to business intelligence projects. This dataset is for a bank which potentially is about to launch a credit card. 

# Column Details: 

    pay_0 to pay-5 is repayment status from april 2005 to Sep 2005 
    -1 pays duly
    1 payment delayed for 1 month 

LIMIT_BILL -  credit limit that has provided by the bank

SEX- 1 is male 2 is female

EDUCATION -
       
    0 -highschool
    1 - University
    2 - graduate school

MARRAGE -
      
    1 - Married
    2 -Single
    3 - others

BILL_AMT1 to BILL_AMT6 (sep 2005 to april 2005) - the amount of money that they had swiped using their ceredit card (in reverse order)
credit card bill

PAY_AMT1 - PAY_AMT6 (sep 2005 to april 2005) what part of the money was returned back by the customer to the bank


WHATEVER HE BORROWED IN BILLAMOUNT COLUMN  AND WHATEVER HE PAID BACK IT IN THE PAYAMOUNT COLUMN

default_payment_next_motnh - who are the defaulter (they have not paid their credit bill back to the company or to the bank) or not 



# Data Cleaning:

1. Replace the values of the SEX first change the type of column from number to text and then replace column value from 1 to Male, 2 to Female.
2. Replace the EDUCATION column first change the type of column from number to text and then replace column value from 1 to Grad School, 2 to University, 3 High School, 0,4,5,6 others.
3. Replace the MARRIAGE column first change the type of column from number to text and then replace column value from 1 to Married, 2 to Single, 0,3 others.
4. Replace column name pay_0 to RS_April 2005 , pay_1 to RS_May 2005, pay_2 to RS_June 2005, , pay_3 to RS_July 2005, pay_4 to RS_August 2005, pay_5 to RS_September 2005.
5. Replace column name BILL_AMT1 to  BILL_AMT September , BILL_AMT2 to BILL_AMT August,........., BILL_AMT6 to BILL_AMT April.
6. Replace column name PAY_AMT1 to PAY_AMT September,....., PAY_AMT6 to PAY_AMT April.

# Add Column:
Total Bill (Custome Column)
Total Payed Back (Custome Column)

# Work on Visualization:

cards:

measure is showing on the card: who will be defaulters in the next month:

    Deafulters = calculate(count(Data[default payment next month]), Data[default payment next month] = 1)

sum of total bills:

first change the column type to decimal 

    sum of bills = sum(Data[Total Bill]) 

repayment status (borrowed money has not returns yet):

    sum of repayments = SUMX(Data, Data[Total Payed Back] * 1)


## pie chart:

defaulters according to there married or educational:
legen : defaulters
details: Education

lot op people wen t to university  are defaulters.

defaulters according to the sex:
legend: defaulters
details: sex

12.54% female are defaulters and 9.58% male are defaulters.

defaulters according to the marriage:
legend: defaulters
details: marriage

10.69% married people are defaulters and 11.14% single people are defaulters.


## clustered column chart:

Monthly payment status:

percentage of customers who are essentially descending into debt. Means they haven't repayed for 1 or 2 months.

represent the payment and repayment status of almost every month.

## conditional formatting  for better visualization

- who are in debt for 1 or more month in red


Has done for every month




limit balance:  how much has the bank set a limit balance for the customers

x_axis - default payment next month
y_axis - Average of LIMIT_BAL

legend - default payment next month


## Stacked Bar Chart:

defaulters by every age group

x_axis - count of default payment next month
y_axis - age

devide the age into bins. right click on y_axis and select new groups

- Age of 21's are the highest number of defaulters






# Final Dashbord:

<img width="723" alt="image" src="https://github.com/user-attachments/assets/1c71ba00-9f7d-4d85-8ec0-d8f7a5af03d0">



