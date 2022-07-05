# Lending Club Case Study
> Lending Club is a finance company which specialises in lending various types of loans to urban customers.
> When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
> * If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
> * If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company


## Table of Contents
* [Problem Statement](#problem-statement)
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## Problem Statement
### Business Understanding
When a person applies for a loan, there are two types of decisions that could be taken by the company:

Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:

* Fully paid: Applicant has fully paid the loan (the principal and the interest rate)

* Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.

* Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 

Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)
### Business Objectives
This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. 

Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'. 

If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 

To develop your understanding of the domain, you are advised to independently research a little about risk analytics (understanding the types of variables and their significance should be enough).

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## General Information
- Steps for EDA :
<ol>
    <li>Data Understanding</li>
    <li>Data Cleaning</li>
    <li>Univariate Analysis</li>
    <li>Bivariate Analysis</li>
    <li>Multivariate Analysis</li>
    <li>Conclusion</li>
</ol>
- Data Set : Loan Lending Club loans 

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
<div class="alert alert-block alert-danger">
    <span style='font-family:Georgia'>
        <b>Factor whether an applicant will be Defaulter: </b> <br><br>
        <b>Continuous Variable: </b>
        <ol>
            <li>LOAN_AMOUNT : Loan amount greater than 15000 dollors have higher default rate</li>
            <li>FUNDED_AMOUNT : Funded amount greater than 15000 dollors have higher default rate</li>
            <li>FUNDED_AMOUNT_INVESTED : Funded amount invested greater than 15000 dollors have higher default rate</li>
            <li>INTEREST_RATE : As Interest rate increases the default rate increases steeply<br>
                (5, 10]-> 6.739748%<br>
                (10, 15]-> 14.820089%<br>
                (15, 20]-> 24.826918% <br>
                (20, 25]-> 38.441558%</li>
            <li>ANNUAL_INCOME : As the annual income increase the default rate decreases</li>
            <li>DTI : As dti increase the default rate increases</li>
            <li>MONTHS_SINCE_LAST_DELINQ  : Crime committed between 90 to 110 days have higher default percent</li>
        </ol>
        <b>Categorical Variable: </b>
        <ol>
            <li>TERM : 60 months term have a higher default rate than 36 months term</li>
            <li>GRADE : As the Grade decreases (A B C D E F G) default rate increases </li>
            <li>SUB_GRADE : As the Sub Grade decreases (A1 A2 B1 B2.....) default rate increases</li>
            <li>VERIFICATION STATUS : Percent of loan defaulted is higher for verifed borrowers</li>
            <li>PURPOSE : Small business borrowers have high default rate</li>
            <li>PUBLIC_BAKRUPTIES_RECORD : One or more pubilc bankruptices have higher default rate</li>
            <li>STATE : Percent of loan defaulted is very high for state NE and high for NV and SD</li>
            <li>EMPLOYEE TITLE : The following have the highest default rate among the top 20 title by frequency:<br>
                walmart                         -> 25.242718%<br>
                united parcel service           -> 22.448980%<br>
                united states postal service    -> 21.118012%<br>
                other                           -> 20.243085%<br>
                at&t                            -> 18.47826%</li>
            <li>ZIP CODE : The following have the highest default rate among the top 20 zip code by frequency:<br>
                917xx    -> 20.882353%<br>
                331xx    -> 20.771513%<br>
                330xx    -> 20.481928%<br>
                913xx    -> 18.867925%<br>
                926xx    -> 18.356164%</li>
        </ol>
    </span>    
</div>

<div class="alert alert-block alert-info">
    <span style='font-family:Georgia'>
        <b>Other suggestions: </b>
        <ul>
            <li>INTEREST RATE AND PUBLIC BANRUPTIES RECORD : Borrowers with lower interest rate and 2 public bankurpties have defaulted</li>
            <li>INSTALLMENT AND PUBLIC BANRUPTIES RECORD : Borrowers with higher installment and 2 public bankurpties have defaulted</li>
            <li>ANNUAL INCONE AND PUBLIC BANRUPTIES RECORD : Borrowers with higher Income and 2 public bankurpties have defaulted</li>
        </ul>
    </span>    
</div>

<div class="alert alert-block alert-success">
    <span style='font-family:Georgia'>
        <b>Decisive Factor whether an applicant will be Defaulter:</b> 
        <ul>
            <li>FUNDED_AMOUNT_INVESTED</li>
            <li>INTEREST_RATE</li>
            <li>ANNUAL_INCOME</li>
            <li>DTI</li>
            <li>TERM</li>
            <li>GRADE</li>
            <li>SUB_GRADE</li>
            <li>PURPOSE</li>
            <li>PUBLIC_BAKRUPTIES_RECORD</li>
        </ul>
    </span>    
</div>

<div class="alert alert-block alert-warning">
    <span style='font-family:Georgia'>
        <b>Factor that may or may not determine whether an applicant will be Defaulter:</b> 
        <ul>
            <li>MONTHS_SINCE_LAST_DELINQ</li>
            <li>PURPOSE</li>
            <li>STATE</li>
            <li>EMPLOYEE TITLE</li>
            <li>ZIP CODE</li>
        </ul>
    </span>    
</div>

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- pandas - 1.3.4
- numpy - 1.20.3
- matplotlib - 3.4.3
- seaborn - 0.11.2
- plotly - 5.8.0

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was group case study for an online advance course.
- https://www.geeksforgeeks.org/
- https://seaborn.pydata.org/
- https://plotly.com/
- https://pandas.pydata.org/
- https://learn.upgrad.com/


## Contact
Created by [@darshil2848] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
