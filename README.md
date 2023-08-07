# Project Description

Hello there :wave:
I hope this project finds you well!

In this project, I will analyze customer behaviour of prepaid packages (Surf and Ultimate) and determine which package generates more revenue.

**Objective**
1. Describe customer behaviour by calculating the mean, variance, and standard deviation of the used calls, message sent, and data usage volume required by users for each package per month.
2. Visualize the customer behaviour


# Steps

1. Data Overview
2. Data Preprocessing
3. Exploratory Data Analysis
4. Hypotheses Testing

## 1. Data Overview

**Data Description** 

Call dataset contains the following columns:

- `id` - Unique call ID
- `call_date` - Call date
- `duration` - Call duration (in minutes)
- `user_id` - ID of the user who made the call

Internet dataset contains the following columns:

- `id` - Unique web traffic session ID
- `mb_used` - Volume of data used during the session (in megabits)
- `session_date` - Web session date
- `user_id` - User ID

Messages dataset contains the following columns:

- `id` - Unique SMS ID
- `message_date` - Date when the SMS was sent
- `user_id` - ID of the user who sent the SMS

Plans dataset contains the following columns:

- `plan_name` - Name of the phone plan
- `usd_monthly_fee` - Monthly fee in US dollars
- `minutes_included` - Monthly call minutes allowance
- `messages_included` - Monthly SMS allowance
- `mb_per_month_included` - Monthly data volume allowance (in megabits)
- `usd_per_minute` - Price per minute if exceeding the plan's call allowance (e.g., if the plan includes 100 minutes, any usage beyond the 100 minutes will incur additional charges)
- `usd_per_message` - Price per SMS if exceeding the plan's SMS allowance
- `usd_per_gb` - Price per extra gigabit of data if exceeding the plan's data allowance (1 GB = 1024 megabits)

Users dataset contains the following columns:

- `user_id` - User ID
- `first_name` - User's first name
- `last_name` - User's last name
- `age` - User's age (in years)
- `reg_date` - Date of subscription registration (dd, mm, yy)
- `churn_date` - Date when the user stopped using the service (if the value is not present, it means the phone plan is still in use at the time of data creation)
- `city` - City where the user resides
- `plan` - Name of the phone plan


## 2. Pre-Processing Data

The following are data preprocessing steps I did in this project:
1. Adding new columns
2. Fixing Data Types
3. Rounding Duration Value
4. Data Aggregation
5. Joining Table
6. Creating Function
7. Drop Unused Column


## 3. Exploratory Data Analysis:

  

1. How is the distribution and descriptive statistics (median, mean, std dev, variance) of telephone usage for each package?
	
**Findings**

- Users of both packages do not exhibit significantly different telephone usage behavior.

- This is evident from the data visualization and descriptive statistics of telephone usage for both packages, which show similar patterns.

- The mean and median telephone usage for both packages are around 400 minutes.

  

**Insight**

- The difference in the maximum duration of telephone calls can be modified to influence users' perception and behavior.

  

**Recommendation**

- For the cheaper package (Surf), the maximum duration of telephone calls can be reduced below the average (e.g., 300 minutes) to potentially increase profits.

- For the more expensive package (Ultimate), the maximum duration of telephone calls can be increased (e.g., to 3500 minutes). However, since the actual usage behavior of users does not exceed 1500 minutes, this change is not expected to result in any loss for Megaline company.

2. How is the distribution and descriptive statistics (median, mean, std dev, variance) of message usage for each package?

**Findings**

- Users of both packages have slightly different message usage behavior.

- This is evident from the data visualization and descriptive statistics of message usage in each package.

- In the Ultimate package, the user distribution tends to be more concentrated, as shown by the Mean and Median values close to each other (around 40).

- In the Surf package, the user distribution tends to be more spread out, as indicated by the difference between the Median and Mean values, and the maximum value reaching above 250.

  

**Insight**

- Adjusting the maximum total messages allowed could impact user behavior.

  

**Recommendation**

- For the cheaper package (Surf), the maximum total messages allowed could be reduced below the average (e.g., 30 SMS) to potentially increase profit.

- For the more expensive package (Ultimate), the maximum total messages allowed could be increased, for example, to 1200 SMS. Although there might be an increase in the maximum total messages, as long as user behavior does not exceed 200 messages, it would not result in losses for Megaline.

3. How is the distribution and descriptive statistics (median, mean, std dev, variance) of internet data usage for each package?

**Findings**

- Users of both packages have similar Median and Mean values, approximately around 17 GB.

- For the Ultimate package, the data usage distribution tends to be more concentrated. This is indicated by the close values of Mean and Median (around 17).

- For the Surf package, the data usage distribution tends to be more spread out. This is shown by the maximum value being above 70GB, with the Mean and Median around 17.

  

**Insight**

- Adjusting the maximum data quota can influence user behavior.

  

**Recommendation**

- For the cheaper package (Surf), the maximum data quota can be reduced below the average (e.g., 12 GB) to increase profit.

- For the more expensive package (Ultimate), the maximum data quota can be increased to 35GB. Although this may lead to a reduction in penalties for the Ultimate package, it is likely to result in an overall increase in profit.

4. How is the distribution and descriptive statistics (median, mean, std dev, variance) of user revenue in the NY-NJ region?

**Findings**

- From February to November, in the NY-NJ region, the revenue from the Ultimate package is higher than the Surf package.

  

**Insight**

- In the long run, the monthly revenue from the Ultimate package has the potential to exceed the revenue from the Surf package.

  

**Recommendation**

- Implement a loyalty program to encourage Ultimate package users to stay with the company for a longer period of time.

5. How is the distribution and descriptive statistics (median, mean, std dev, variance) of user revenue outside NY-NJ region?

**Findings**

- The high penalty leads to a significantly higher total income for the Surf package outside the NY-NJ region compared to the Ultimate package.

  

**Insight**

- Penalties have a significant impact on increasing the total income.

  

**Recommendation**

- Adjusting the maximum value and penalty rates for each package can potentially increase overall profit.

6. How is the distribution and descriptive statistics (median, mean, std dev, variance) of the number of users for each package in each city group?

**Findings**

- There are more Ultimate users outside the NY-NJ region.

- There are more Surf users within the NY-NJ region.

  

**Insight**

- Two distinct market segments have formed, one within the NY-NJ region and the other outside the NY-NJ region. People within the NY-NJ region tend to choose more cost-effective internet packages.

  

**Recommendation**

- Focus on increasing Surf users in the NY-NJ region and Ultimate users outside the NY-NJ region.

7. How is the distribution of penalty amounts for each package (ultimate and surf)?

a. call duration

**Findings**

- Ultimate users did not exceed the phone call duration, so no penalty was applied.

- Surf users dominate the penalty application due to exceeding the maximum allowed phone call duration.

- The likelihood of Surf users exceeding their phone call usage is 30%.


**Insight**

- With the high penalty rate for Surf users, it is possible to adjust the penalty rate and the maximum value.

  
**Recommendation**

- Create additional phone call packages for Surf users.

b. sent messages

**Findings**

- Ultimate users did not exceed the SMS usage, so no penalty was applied.

- Surf users dominate the penalty application due to exceeding the maximum allowed SMS usage.

- The likelihood of Surf users exceeding their SMS usage is 21%.

  

**Insight**

- With the high penalty rate for Surf users, it is possible to adjust the penalty rate and the maximum value.

  

**Recommendation**

- Create additional SMS packages for Surf users.

c. quota internet

**Findings**

- Surf users still dominate the penalty for exceeding the data usage, reaching up to 600 USD.

- Surf users dominate the penalty application due to exceeding the maximum allowed data usage.

- The likelihood of Surf users exceeding their data usage is 57%, and the likelihood of Ultimate users exceeding their data usage is 5%.

  

**Insight**

- With the high penalty rate for Surf users, it is possible to adjust the penalty rate and the maximum value.

  

**Recommendation**

- Create additional data packages for Surf users.

# Hypotheses Testing

#### Hypothesis 1: The average income of users of the Ultimate and Surf phone packages is not the same

**Verdict**

The usage of phone packages in both Surf and Ultimate packages is the same.

This means that despite subscribing to different packages, user behavior in phone call duration is the same for both packages.

**Insight**

Creating an extra package to meet the over-duration needs in the Surf package.

#### Hypothesis 2: The average income of users in the NY-NJ region differs from the income of users from other regions.

**Verdict**


The total income from the Surf and Ultimate packages differs.

Meaning: Due to the difference in rates for each package, the number of users and pricing strategies, as well as penalty costs, have a significant impact.  

**Insight**

Penalty costs have a considerable influence on the total income. Surf users still account for the majority of the penalties that need to be paid. Adjusting the penalty fees could potentially increase profits.

#### Hyphotesis 3: The average income of users in the NY-NJ region is the same as the income of users from other regions

**Verdict**


The income of users in the NY-NJ region differs from the income of users from other regions.

Meaning: NY-NJ has its own identity compared to other regions. This will affect the marketing strategies implemented.


**Insight**

The thrifty behavior in the NY-NJ region serves as a benchmark to focus on increasing Surf users in the NY-NJ region.

# General Conclusion

1. Penalties have a significant impact on the total income for both packages, both in the NY-NJ region and outside the NY-NJ region. Surf users dominate the number of penalty payments, presenting an opportunity to create extra max value for Surf users.

2. Due to the considerable gap between the two packages, it is also worth considering the creation of a new package that falls in between them.

3. Despite the higher subscription cost, the highest income is obtained from Surf users  

4. The accepted H1 hypotheses are as follows:

	- The average income of Surf and Ultimate package users differs.
	- The average income of users in the NY-NJ region differs from the income of users from other regions.
5. The NY-NJ region is a potential area as it is dominated by Surf users.
