# GloboCom Case Study

Background:

A telecommunications company, Globo-Com, is concerned because the percentage of their customers who are leaving the company for another service provider (referred to as churn) is too high.  A new CEO has recently joined Globo-Com and has asked the various functions (i.e. Marketing, Finance, Sales, Product) for their evaluation on how best to decrease the churn rate, ultimately helping to drive growth in market share.  Below are the various options being pitched by each of the different functions.

# Your Task:

The CEO has asked for your help in evaluating these options.  Specifically, do you agree with any of these proposals?  Why or why not?  Are there any changes you would make to any proposals to make them more impactful?  Do you have any other ideas that Globo-Com should consider?  Data has been provided from a random sampling of 10% of the company’s customers last year.  Use this data to evaluate the proposals (below) and provide a recommendation to the CEO to accept, reject, or modify these proposals and any additional recommendations you think are necessary.

# Proposals:

1.	Finance believes that churn percentage is a misleading indicator because it assumes all customers are equal.  They think most of our churn is from low-value customers and therefore has little impact on revenue.  Instead of trying to reduce churn, Globo-Com should stop marketing spend in this low-value, high churn segment to increase profitability. 
2.	Marketing believes Globo-Com needs to focus on being competitive specifically with its biggest competitor, Average Joe’s Wireless.  Average Joe’s Wireless recently ran a large campaign advertising it’s new international plan.  Marketing recommends further developing Globo-Com’s option – expanding into more countries than Average Joe’s for only a slightly higher cost.
3.	Sales is requesting 10 additional heads be added to account management/customer service.  Each will make ~40K annual salary.  This added expense will be more than offset by the revenue this team saves the company by minimizing churn.
4.	Operations wants additional time and resources to build a model that identifies groups (or segments) of customers with similar behaviors.  They believe a predictive model could be produced to inform strategic customer relationship programs for mitigating churn.  They have done some prelim exploratory data analysis and have found some trends.

# Overview and Approach

Globo-Com currently has $24M in annual revenue and is losing $3.8M annually to competitors for a churn rate of 16%. I utilized Python to manipulate and analyze the data from the provided CSV file

# Recommendations:

## 1. Finance

First, I considered Finance's proposal that overall churn percentage is misleading, and that Globo-Com should reduce marketing spend in low-value customers whose churn has low financial impact to increase profitability. With the data's limitations, I made the assumptions that marketing spend is allocated equally across customers of all sizes, and that churn percent is based on the number of churn customers and not total spend of churn customers. 

I looked at customer churn count rather than the overall percentage and broke out customers into spend ranges to determine the largest churn segments. Based on this, it is easy to see that the highest level of churn is in customers with high spend. 

![churn_hist](https://user-images.githubusercontent.com/68552052/222923407-30e3f89a-b4f7-4150-aa93-6a0ae550444e.png)

Churn in the low spend range, from $20-$50, only makes up about 10% of total churn dollars, while in the high spend range it is over 50%. Since marketing spend is considered equal for customers at all spend ranges, the proportion of churn dollars to marketing spend is too heavily weighted on low spend customers. I would accept Finance's proposal that Globo-Com should reduce marketing spend in low value customers. 

## 2. Marketing

Marketing plans to focus on it's competition with Average Joe's Wireless and expand Globo-Com internationally to reduce churn. I made the assumption that the additional cost of the internation advertising campaign is negligible. 

I again used the overall customer spend range histogram and duplicated this for international customers. If you compare the two, there is a clear image of higher churn amongst international plan customers. 

![intl_hist](https://user-images.githubusercontent.com/68552052/222924474-ae89eb6f-35be-4bd1-b91d-335acd5c9a87.png)

To explore this relationship deeper and consider outliers, I also constructed a box and whiskers chart to display the international spend % ranges in churn vs. non-churn customers. There does not appear to be much variance in international spend % between churn and non-churn customers. Also, at $0.27 per minute, the international plan creates a lot of overlap to 

![image](https://user-images.githubusercontent.com/68552052/222925007-a7812882-7a02-46ec-8d40-622cfb1a438f.png)

I would reject Marketing's proposal to expand the international plan to reduce churn. There are not many international users and at such a high cost there is not much benefit to the plan. Instead, Globo-Com should focus on cost-reduction to decrease churn.

## 3. Sales

Sales believes that hiring 10 additional heads in customer service at a cost of $400K annually will help reduce churn. Here I made the assumptions that Globo-Com currently struggles with customer service volume and that additional service reps will help reduce the call volume. 

I wanted to look at churn % across each service call volume to see if there is a relationship between high service calls and churn. 

![image](https://user-images.githubusercontent.com/68552052/222927120-c69246fa-4a1e-4e86-845e-66588a1069bf.png)

I would accept Sales' proposal to add additional customer service reps on the basis that these reps will reduce service call count. The $400K investment annually can work to reduce churn by $800K per year if the customers with high volume (5 calls and over) are addressed.

## 4. Operations

The Operations team has proposed adding resources to build a predictive model that will analyze customer behavior and diagnose causes of churn. 

## 5. Additional Considerations
