# Machine Learning Case Study: predicting minimum cost of a bank's telemarketing campaign
A Data Science Machine Learning approach to predict the best candidates to be targeted for a marketing campaign

**About the project**

This Machine Learning project is based on the 2014 original study: "A data-driven approach to predict the success of bank telemarketing" (can be found here) in which the authors conducted a Data Mining (DM) project to predict the success of telemarketing calls for selling bank long-term deposits of a Portuguese retail bank.

Source: [Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014

**Dataset Information**

The dataset used for the current case study has 41188 samples and 16 inputs.

    bank_marketing_campaign.csv can be downloaded here: https://bit.ly/31a0EAL

There are also 4 original datasets:

    bank-additional-full.csv with all examples (41188) and 20 inputs, ordered by date (from May 2008 to November 2010), very close to the data analyzed in [Moro et al., 2014]
    bank-additional.csv with 10% of the examples (4119), randomly selected from 1), and 20 inputs.
    bank-full.csv with all examples and 17 inputs, ordered by date (older version of this dataset with less inputs).
    bank.csv with 10% of the examples and 17 inputs, randomly selected from 3 (older version of this dataset with less inputs).

You can download the zip file (4 datasets) here. The smallest datasets are provided to test more computationally demanding machine learning algorithms (e.g., SVM). The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).

**Attribute Information**

The dataset contains information about all customers targeted by the campaign. Next, all the input variables:
Bank client data:

    age (numeric)
    job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
    marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
    education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
    default: has credit in default? (categorical: 'no','yes','unknown')
    housing: has housing loan? (categorical: 'no','yes','unknown')
    loan: has personal loan? (categorical: 'no','yes','unknown')

Other attributes:

    pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
    previous: number of contacts performed before this campaign and for this client (numeric)
    poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

Social and economic context attributes:

    emp.var.rate: employment variation rate - quarterly indicator (numeric)
    cons.price.idx: consumer price index - monthly indicator (numeric)
    cons.conf.idx: consumer confidence index - monthly indicator (numeric)
    euribor3m: euribor 3 month rate - daily indicator (numeric)
    nr.employed: number of employed citizens - quarterly indicator (numeric)

Output variable (desired target):

    y - has the client subscribed a term deposit? (binary: 'yes','no')

**The current case study**

From the data collected between 2008 and 2015, which includes data related with the recent financial global crisis that severely affected Portugal, the dataset stores information of a direct marketing campaign (phone calls) developed and implemented by the bank's marketing department in order to attract customers to subscribe term deposits, collecting and classifying the results as a binary categorical label: 'yes' and 'no'.

Until that time, their communication strategy was to reach the maximum number of clients, indiscriminately, and try to sell them the financial product over the phone. However, that approach, in addition to spending more resources because it would involve having several people calling all customers and also it used to consume a lot of time, it was also very uncomfortable for a vast number of clients who was wishing not to be disturbed by this type of action.

In order to determine the costs for the campaign to be successful, the marketing team has reached to a conclusion:

    For each customer identified as a good candidate and therefore defined as a target of the campaign but doesn't subscribe the term deposit, the bank had a cost of 500 EUR.
    For each customer who was identified as a bad candidate and therfore excluded from the target of the campaign but was actually a good candidate and would subscribe the product, the bank had a cost of 2000 EUR.

**Machine Learning problem and objectives**

We're facing a binary classification problem. Based on the above costs information, the goal is to train the best machine learning model that is able to predict and select the optimal number of candidates to be targeted by the campaign in order to reduce costs and maximizing efficiency.
Project structure

The project is divided into three main categories:

    EDA: Exploratory Data Analysis
    Data Wrangling: Cleaning and Feature Engeneering
    Machine Learning: Predictive Modelling

In this article, I'll be focusing only on the first section, the Exploratory Data Analysis (EDA). EDA usually reveals important insights about the data that can be (and usually is) used to build the predictive model and it can also help the data scientist to clearly identify the cleaning and feature engeneering steps.

**Performance Metric**

The performance metric in use for evaluation is the total costs (EUR) since the objective is to determine both minimum costs and maximum efficiency of the marketing campaign.
