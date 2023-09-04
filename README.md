![image](https://github.com/hAri0520/Health-Insurance-Premium-prediction/assets/138093343/b7d79686-db1b-49d2-8d6c-bd04de5d3b43)# Health-Insurance-Premium-prediction

### Context:
An insurance company in the US is reviewing its insurance claims/charges and is trying to do a cause and effect analysis for future business decisions. It has collected data for its customers who have made claims till recent time. The data-points collected are age, gender, bmi, number of children/dependents, smoking habit, region they belong to, charges/bills claimed under the insurance. This analysis would have a bearing on what premium should the company charge a customer availing an insurance policy.

### Business objective:
The objective is to do a cause and effect analysis on historic-data of insurance claims and predict how much premium amount should  the company it's customers.

### Approach:
 #### Excel Analysis
   1. To understand the given data the histograms and box plots were used and primary EDA have been carried out and following insights were gathered.
         i. The demography that we are looking at has more no. of young people in the age bracket of 18-30
        ii. More no of people have lesser insurance charges, whereas lesser no of people have high insurance charges, It would be interesting to know who are these people
       iii. Age and charges graphs slightly hint that middle aged people and probably older people might be getting billed more under the insurance
        iv. Is age the only factor or are there more factors contributing to the insurance charges ?
         v. BMI is distributed normally
        vi. Charges and bmi have outliers, these might be some points to study separately, whether higher bmi is causing higher health problems and claims as result
      
  2. The correlation between the fields age, bmi and charges were analysed to gather the information about how they are related.
  3. Various pivot tables and cahrts were introdeced to understand the following fields
        i. Male/Female ratio and share information on which gender has more smokers
       ii. Charges vs Age
      iii. Charges vs BMI
       iv. Charges for Smokers vs Non-smokers 
  
  4. The regionwise smokers ratio and the premium charged to a smoker were analysed and it was determined tha a smoker from a southeast region was charged the most.
  5. The number of family members in the climants family also have effects on the charge. a person with 2 and 3 choldern was charged more than others.

With all these done and after a good understanding of the dataset and the fields within the data was being prepared for Regression.
  1. The Categorical columns were encoded and converted into Numerical columns.
  2. First regression has been carried out and the follwoing insights were gathered.
       i. On checking the normality plot we see the data is not a perfectly normal-distributed data, because we saw many outliers; these outliers could be natural outliers															
      ii. R-square values are good enough for real-life case study															
     iii. The observation for regions is to be interpreted w.r.t 'northeast' region															
      iv. We observe that charges for southeast region reduces wr.r.t northeast region, contrary to our expectation from EDA															
       v. We should try another regression analysis with "northwest" and "sex" variables dropped.
  
  3. The second regresson gave the following insights
         i. smoker, age, bmi, no. of children are important variables in that order of their t-stat values
        ii. southeast region has a negative relation with charges (this is w.r.t. northeast), meaning people from this region claim lesser than others
       iii. southwest region doesn't come out to be a significant variable
        iv. Standardised residuals show no deviating pattern, means there is no heteroscadasticity
  
  4. However we should also check for combined effect of region and smoking habbit so three mmore columns were added.
  5. And third regression has been caried out	which shows that sex, northwest and northwest_smoker are not significant variables So we will run one more regression with these variables dropped
  6. The final regression has been carried out and final insights which that have been collected were
         i. Smoker, age, bmi have a very strong and direct impact on increasing insurance charges claim
        ii. Also a smoker in southeast and southwest region will claim higher charges
       iii. If we look at only the region as an idependant variable then people from south east and south west region claim lesser charges w.r.t our reference region northeast
        iv. Claimants having more no. of children also show higher claims

### Tools used: Advanced Excel, Python(NumPy, Pandas, Statsmodel)
