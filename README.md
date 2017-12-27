# Ultimate-Challenge
Ultimate Challenge

A ride-sharing data science challenge with exploratory data analysis, experiment/metrics design, and predictive modeling.

Part 1 ‑ Exploratory Data Analysis

The attached logins.json file contains (simulated) timestamps of user logins in a particular geographic location. Aggregate these login counts based on 15 minute time intervals, and visualize and describe the resulting time series of login counts in ways that best characterize the underlying patterns of the demand.

Please report/illustrate important features of the demand, such as daily cycles. If there are data quality issues, please report them.

Answer:

Amount of user-logins increase and peak torwards the weekend. Amount of user-logins increase during lunch time (11- am to noon) and during late-night (9 pm - 4 am)

Part 2 - Experiment and metrics design

The neighboring cities of Gotham and Metropolis have complementary circadian rhythms: on weekdays, Ultimate Gotham is most active at night, and Ultimate Metropolis is most active during the day. On weekends, there is reasonable activity in both cities.

However, a toll bridge, with a two way toll, between the two cities causes driver partners to tend to be exclusive to each city. The Ultimate managers of city operations for the two cities have proposed an experiment to encourage driver partners to be available in both cities, by reimbursing all toll costs.

What would you choose as the key measure of success of this experiment in encouraging driver partners to serve both cities, and why would you choose this metric?

Describe a practical experiment you would design to compare the effectiveness of the proposed change in relation to the key measure of success. Please provide details on:

how you will implement the experiment.
what statistical test(s) you will conduct to verify the significance of the observation.
how you would interpret the results and provide recommendations to the city operations team along with any caveats.
Answer:

First, we talk about why the Ultimate managers want more driver partners to be available in both cities.

To increase driver/rider acceptance-rates
To increase driver/rider sign-ups
To reduce driver/rider wait times
To increase profit
Ultimately, increasing acceptance-rates and sign-ups while reducing wait times would lead to profit. (No pun intended) In order to increase profit, the additional income brought in during the experiment must outweigh the toll cost reimbursements. We would use the key metric of profit after reimbursement.

There are two tests that we could do depending on the time and budget available. A simple study could be an A/B study. We would randomly select half of the drivers to participate in the study while we leave out the other half. After a few months, we compare the profit made after reimbursement of toll costs. A more robust study could last a year. All driver partners are included in the study and the profit made for the year is compared to the previous years with time series analysis.

After getting our results, we would use a t-test to test for significance (p = 0.05) between each group.

The results of this experiment all depend on what we started it for. An increase in profits. If profits decreased after the experiment, it would mean that reimbursement of toll fees may not have been the most effective way to encourage drivers to be active in both cities in order to increase profits. There may have been exploitations of the incentive or worse. If profits stay the same, then the feature should be left intact due to the possible convenience to some drivers. Finally, if profits increase, it could mean that more experiments relating reimbursements such as gas or mileage will increase profits even further.

Part 3: Predictive modeling

Ultimate is interested in predicting rider retention. To help explore this question, we have provided a sample dataset of a cohort of users who signed up for an Ultimate account in January 2014. The data was pulled several months later; we consider a user retained if they were “active” (i.e. took a trip) in the preceding 30 days.

We would like you to use this data set to help understand what factors are the best predictors for retention, and offer suggestions to operationalize those insights to help Ultimate. The data is in the attached file ultimate_data_challenge.json. See below for a detailed description of the dataset. Please include any code you wrote for the analysis and delete the dataset when you have finished with the challenge.

1. Perform any cleaning, exploratory analysis, and/or visualizations to use the provided data for this analysis (a few sentences/plots describing your approach will suffice). What fraction of the observed users were retained?

2. Build a predictive model to help Ultimate determine whether or not a user will be active in their 6th month on the system. Discuss why you chose your approach, what alternatives you considered, and any concerns you have. How valid is your model? Include any key indicators of model performance.

3. Briefly discuss how Ultimate might leverage the insights gained from the model to improve its longterm rider retention (again, a few sentences will suffice).
Data description

city: city this user signed up in
phone: primary device for this user
signup_date: date of account registration; in the form ‘YYYY MM DD’
last_trip_date: the last time this user completed a trip; in the form ‘YYYY MM DD’
avg_dist: the average distance in miles per trip taken in the first 30 days after signup
avg_rating_by_driver: the rider’s average rating over all of their trips
avg_rating_of_driver: the rider’s average rating of their drivers over all of their trips
surge_pct: the percent of trips taken with surge multiplier > 1
avg_surge: The average surge multiplier over all of this user’s trips
trips_in_first_30_days: the number of trips this user took in the first 30 days after signing up
ultimate_black_user: TRUE if the user took an Ultimate Black in their first 30 days; FALSE otherwise
weekday_pct: the percent of the user’s trips occurring during a weekday
Answer

37.6% of all users retained. (6 months)
Used neural network to get 77% accuracy predictive model.
The features most correlated to retention are: Users in King's landing, iPhone users, and high trips in first 30 days. In order for Ultimate to further improve retention rates, they should look into what is different in King's landing compared to other cities. They should also test usability between iPhone and Android to see if retention is related to features in the app or something else. Finally, taking many trips in the first 30 days is beneficial to retention rates. Ultimate could give out more promotions for first-time users to gain consumer loyalty.
