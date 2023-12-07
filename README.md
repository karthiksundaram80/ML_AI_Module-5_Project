# ML_AI_Module-5_Project
Will a Customer Accept the Coupon? -- Practical_Application_Assignment_5.1_Karthik_Sundaram
### Coupon Acceptance Analysis

The objective of this activity is to determine the acceptance of coupons by drivers using various features presented in the dataset.

## The following are the transformations done on the variables
* Feature "Car" was dropped due to 99 % of its values being missing.
* A few other features are missing less than 2 % of its value. For those missing values, the mode of those feature values was calculated and populated. 
* Feature "toCoupon_GEQ5min" contained only one value which was 1. Therefore the column was dropped
* Features "direction_same" and "direction_opp" are mutually exclusive. So the column "direction_opp" was dropped as its value can be inferred from the other variable.

## Determining the Top 3 correlating features
![HeatMap_of_Correlation_Matrix_of_all_Features](https://github.com/karthiksundaram80/ML_AI_Module-5_Project/assets/42277105/d1cbdcc3-9315-403b-8143-d8c81e82f7cd)


## Analysis of bar coupon
* The proportion of bar coupons accepted is 41.0 %.
* No bar coupons were accepted by the drivers having <b>kids</b> as passanger
* Below is the <b>visual of the acceptance and rejection rate of bar coupons based on the categorical features of the dataset.</b>
![Acceptance_and Rejection_Rates_of__coupons_by_ various_Features](https://github.com/karthiksundaram80/ML_AI_Module-5_Project/assets/42277105/3a002f15-9ab1-4f19-a2f7-931ceaf921a8)


* Proportion of bar coupons accepted by driver's destination and if the coupon venue is in the same direction as that of destination.
  - Drivers not travelling to any <b>urgent place</b> have the highest acceptance rate at <b> 20.72 %</b> when the venue is in the opposite direction as that of the destination.
  - Drivers travelling <b>home</b> have an <b>8.28 %</b> acceptance rate when the venue is in the same direction. If the venue is in the opposite direction, then the acceptance rate drops to <b>3.17 %</b>
  - Drivers travelling to <b>Work</b> have a <b>1.29 %</b> acceptance rate when the venue is in the same direction. If the venue is in the opposite direction, then the acceptance increases to <b>7.54 %</b>
  
* Analysis based on the frequency of drivers going to the bar:
  - Acceptance rate of drivers going to bar <b>less than 3 times</b> a month has the highest rate at <b>33.42 %</b> than the drivers who went to bar <b>more than 3 times</b> a month having the acceptance rate of <b>7.59 %</b>.
  ![df_bar_3_or_less_and_df_bar_more_than_3](https://github.com/karthiksundaram80/ML_AI_Module-5_Project/assets/42277105/45b45bc8-c019-4421-bc54-38ad8c2f5ea5)

* Below is the <b> visual of the acceptance rate of bar coupons by occupation</b>
  ![Acceptance_rate_ of _coupons_ by_ occupation](https://github.com/karthiksundaram80/ML_AI_Module-5_Project/assets/42277105/19d3ceb2-472e-440e-974b-b0dbbfd6a8d2)



* <b>Student</b> and <b>Unemployed</b> have the highest acceptance rate for coupon at <b>6% and 5%</b> respectively.
* Proportion of bar coupons accepted by drivers who are currently employed. We need to remove the occupations <b>Student</b>, <b>Unemployed</b> and <b>Retired</b> as these belong to not working category.
  - Drivers who are <b>working</b> and over 25 years old had a much higher <b>(24 %)</b> acceptance rate than drivers who are <b>working</b> and under 25 years old <b>(5%)</b>.

## Analysis of Restaurant(20-50) coupon
* Proportion of expensive restaurant coupons (Restaurant(20-50)) accepted is 44.1 %
* Below is the <b>visual of acceptance and rejection rates of restaurant coupons based on the categorical features of the dataset.</b>
![Acceptance_ and_ Rejection_ Rates_ of_ expensive_ restaurant _coupons_ by_ various_Features](https://github.com/karthiksundaram80/ML_AI_Module-5_Project/assets/42277105/181df3da-a781-49f3-996f-97c3106f42c7)
 

* Proportion of coupons accepted by drivers who went to restaurants 3 or fewer times a month to those who went more.
  - Drivers who went to restaurant <b>more than 3 times a month</b> accepted <b>fewer</b> coupons (5.3 %) than drivers who went <b>less than 3 times</b> (39 %). Also,
    Drivers with age <b>over</b> the median age of <b>31 years </b> accepted <b>less</b> coupons than drivers <b>under 31</b>.
    
 ##### Since drivers who went to restaurants less than 3 times accepted more coupons, let us include other features to this data to see how the acceptance rate is affected.
 * Check the income distribution of drivers who go to a restaurant less than 3 times a month and accept coupon
   - There is no big difference in acceptance rate between low and high-earning drivers; 50.95 % vs 49 %.
     
 * Compare the acceptance rate of drivers going to restaurants less than 3 times a month against their working status. We will consider students and unemployed as not working and other occupations as working.
   - Drivers who went to restaurant <b>less than 3 times</b> and are <b>employed</b> accepted more coupons (29%) than drivers who are either unemployed or a student (9%).
     
 *  Compare the acceptance rate of drivers going to restaurants less than 3 times a month against the proximity of their destination to the restaurant venue. Here, value 1 indicates time to venue is within the given minute and 0 indicates time to venue is not within the given minute.
    - For distance to venue less than or equal to 15 mins, drivers going in the opposite direction going in opposite direction accepted more coupons <b>(20%)</b> than drivers travelling in same direction <b>(1%)</b>. This is because all drivers going <b>home</b> as their destination aren't accepting many coupons.
