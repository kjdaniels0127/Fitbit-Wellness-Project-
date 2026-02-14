# Fit Bit Wellness Project 
This is a repository of the key visualizations and tech tools I used in FitBit Wellness Project. In addition, the key data insights that I gleaned from analyzing the smart consumer watch data to track patterns. Here's more detail about the business purpose of this project. 

**Project Summary** 

Urksa Srsen believes that analyzing Bellabeat app consumer usage can help the company unlock new insights that can guide Bellabeat’s marketing strategy to grow the company and assist in becoming a larger player in the global market. The goal of this project is to analyze smart device usage data to gain insight into how consumers are using the smart device and then use these insights to come up with recommendations to help guide the marketing strategy for the company. 

I.	Project/Client Summary
1. **Client:**
- Bellabeat, a high-tech manufacturer of health-focused products for women. This company is a successful small company. There’s potential for them to become a larger player in the global smart device market. 
- Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
- Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team
- Bellabeat marketing analytics team: A team of data analysts responsible for collecting, analyzing, and reporting data that helps guide Bellabeat’s marketing strategy. You joined this team six months ago and have been busy learning about Bellabeat’’s mission and business goals — as well as how you, as a junior data analyst, can help Bellabeat achieve them.
2. **Products**
- Bellabeat app: The Bellabeat app provides users with health data related to their activity, sleep, stress, menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and make healthy decisions. The Bellabeat app connects to their line of smart wellness products.
- Leaf: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects to the Bellabeat app to track activity, sleep, and stress.
- Time: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your daily wellness.
- Spring: This is a water bottle that tracks daily water intake using smart technology to ensure that you are appropriately hydrated throughout the day. The Spring bottle connects to the Bella beat app to track your hydration levels. 
- Bellabeat membership: Bellabeat also offers a subscription-based membership program for users. Membership gives users 24/7 access to fully personalized guidance on nutrition, activity, sleep, health and beauty, and mindfulness based on their lifestyle and goals.

## Questions and My Predictions Pre-Data Analysis Phase

1. What are some trends in smart device usage?
i.	Prediction: I think first the more active a user is, the more water they will tend to consume and vice versa. I’ll also say the more the user practices mindfulness activities so activities like (meditation, yoga, etc.) the lower their stress levels are during the day and vice versa. Lastly, I will say the more active a user gets the more quality sleep they tend to get and the healthier their eating habits are. I’d be interested in particular to explore the relationship between calories burned and weight. Like do underweight people tend to burn less calories and overweight people tend to burn more calories and vice versa. I also would like to explore the relationship between calories and METs (energy expenditure) and see how these two variables impact each other. I think there is a positive correlation between calories burned and METs used.

2. How could these trends apply to Bellabeat customers?
i.	Prediction: I think these trends can help us gain more clarity around Bellabeat’s customer activity habits, mindfulness habits, and their overall stress levels. I can then with these insights then come up with recommendations as to how Bellabeat can maximize their wellness and health. For instance, I say that the more active a user is the more water they tend to consume. If this is true, then a good recommendation would be for Bellabeat to invest more in hydration materials to encourage the Bellabeat customers to exercise more.

3. How could these trends help influence Bellabeat marketing strategy?
i.	Prediction: If for example, the more active a user is the more water they tend to consume. Bellabeat could advertise more wellness products that encourage people to exercise more often. They could even offer discounts for more active consumers. Another example is let’s say that the meditation and yoga practices do in fact lead to lower stress levels. What Bellaboat could do is put more money into advertising for their medititation and yoga practice programs. They could also offer discounts and incentives for the women to use yoga or other mindfulness programs to help women’s health and emotional well being increase.

## Data Preparation Phase and Data Limitations

**Datasets Used** 

|     Dataset Name                       |     Dataset Description                                                                                                                                                             |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     dailyactivity_merged               |     Collects the daily activity of the 33-35 fitibit users   which includes calories burned, active minutes, sedentary minutes, steps, and   distance over 03.12.2016-05.12.2016    |
|     heartrate_seconds_merged           |     Exact heart rate by minute and day for 15 fitbit users   over 03.12.2016-05.12.2016                                                                                             |
|     hourlycalories_merged              |     Calories burned by the hour for 35 fitbit users over   03.12.2016-05.12.2016                                                                                                    |
|     hourlyintensities_merged           |     Hourly and average intensities for 35 fitbit users over   03.12.2016-05.12.2016                                                                                                 |
|     hourlysteps_merged                 |     Hourly steps count for 34 fitibit users from   03.12.2016-05.12.2016                                                                                                            |
|     minutesCalroiesNarrow_merged       |     Calories burned by the minute for 35 fitbit users over   03.12.2016-05.12.2016                                                                                                  |
|     minutesIntensitiesNarrow_merged    |     Minute Intensities for 35 fitbit users over   03.12.2016-05.12.2016 (each minute is one row)                                                                                    |
|     minutesMETSNarrow_merged           |     METs (metabloic equivalents) expended by minute for 34   fit bit users over 03.12.2016-05.12.2016                                                                               |
|     minuteSleep_merged                 |     Sleep day table breaking down total asleep time, total   time in bed, and sleep records for 24 fit bit users                                                                    |
|     minuteStepsNarrow_merged           |     Steps recorded for dates 03.12.2016-05.12.2016 for 34   users                                                                                                                   |
|     weightloginfo_merged               |     Weight info broken down by BMI, weights in lbs and kgs   for 13 fitibit users over 03.30.2016-05.12.2016                                                                        |
|     dailycalories_merged               |     Calories burned daily for 35 fitbit users over   04.12.2016-05.12.2016                                                                                                          |
|     dailyIntensities_merged            |     Daily Intensities for 33 fitbit users measuring active   and sedentary minutes and distances for 04.12.2016-05.12.2016                                                          |
|     dailysteps_merged                  |     Daily steps count for 33 fitbit users from   04.12.2016-05.12.2016                                                                                                              |
|     minutesCalroiesWide_merged         |     Calories burned by the minute for 33 fitbit users over   04.13.2016-05.12.2016 (each minute has a separate column)                                                              |
|     minutesIntensitiesWide_merged      |     Minute Intensities for 35 fitbit users over   03.12.2016-05.2016 (each minute is one column)                                                                                    |
|     minutesStepWide_merged             |     Minutes steps for 33 fitbit users                                                                                                                                               |
|     sleepday_merged                    |     Sleep day table breaking down total asleep time, total   time in bed, and sleep records for 24 fit bit users                                                                    |


**Data Limitations**
1. Some datasets don’t have the full 35 users in it (Ex. Heart Rate and Weight Datasets only have 14 and 13 users in it, respectively.)
2. Only women have been provided
3. We don't have data about these women's race, disability, or age. 
4. This leads to the possibility of sampling bias due to limit demographic info. 

## FitBit Categories Studied and Unique FitBit Names 

**Fitbit Categories Studied**
1. Steps
2. Intensities
3. Calories 
4. fitbit User Weight
5. Heart Rate
6. METS
7. Daily Activity
8. Sleep Minutes


**Unique FitBit Names**

|     User IDs      |     Unique Fit Bit   User Name    |
|-------------------|-----------------------------------|
|     6117666160    |     User 1                        |
|     7086361926    |     User 2                        |
|     8792009665    |     User 3                        |
|     3977333714    |     User 4                        |
|     8583815059    |     User 5                        |
|     1624580081    |     User 6                        |
|     4558609924    |     User 7                        |
|     2891001357    |     User 8                        |
|     4445114986    |     User 9                        |
|     3372868164    |     User 10                       |
|     6962181067    |     User 11                       |
|     1644430081    |     User 12                       |
|     2026352035    |     User 13                       |
|     8053475328    |     User 14                       |
|     1844505072    |     User 15                       |
|     8378563200    |     User 16                       |
|     2022484408    |     User 17                       |
|     4057192912    |     User 18                       |
|     4020332650    |     User 19                       |
|     7007744171    |     User 20                       |
|     6290855005    |     User 21                       |
|     1503960366    |     User 22                       |
|     4702921684    |     User 23                       |
|     1927972279    |     User 24                       |
|     4319703577    |     User 25                       |
|     2347167796    |     User 26                       |
|     5553957443    |     User 27                       |
|     2873212765    |     User 28                       |
|     5577150313    |     User 29                       |
|     6775888955    |     User 30                       |
|     6391747486    |     User 31                       |
|     8253242879    |     User 32                       |
|     8877689391    |     User 33                       |
|     2320127002    |     User 34                       |
|     4388161847    |     User 35                       |









**Data Visualizations and Insights for Fit Bit Wellness Project**

## Data visualizations for Wellness Fitbit Tech: Consumer Trend Analysis 

![Average Intensity and Average Sleep Minutes per day](https://github.com/user-attachments/assets/f695479e-48ee-438f-bb4b-efedff4a808d)
Based on the available data for the 30 Fitbit users, there seems to be no straightforward correlation between average intensity and average sleep minutes per day. 

![Average METS and Calories per Fitbit ID](https://github.com/user-attachments/assets/be11ffd5-7634-4a2a-8e49-b277d38f0173)
Based on the available data for 30 Fitbit users, there appears to be a positive correlation between average METs and average daily calories burned. 
No notable outliers based on available data. 
![Average Sleep Minutes and Average Calories per day](https://github.com/user-attachments/assets/44af2726-e36a-425f-891e-0e576ca147fe)
Based on the available data for the 30 fitbit users, there seems to be a slight positive correlation between average calories burned and average sleep minutes per day. 
There are a few notable outliers among Fitbit users: all above the 75th percentile (Quartile 3) in daily sleep minutes and below the 25th percentile (Quartile 1) in daily calories. 
The 25th percentile or Quartile 1 is 1904.48 for daily average calories and the 75th percentile or Quartile 3 is 488.33 for daily average sleep minutes 
a.	User 4: 1416.69 average calories and 594.12 average sleep minutes per day.
b.	User 15: 1523.53 average calories and 729.55 average sleep minutes per day. 
c.	User 27: 1821.51 average calories and 538.51 average sleep minutes per day.
d.	User 13: 1494.97 average calories and 535.96 average sleep minutes per day. 

![Average Sleep Minutes and Average Heart Rate](https://github.com/user-attachments/assets/8ba40ced-c457-4bf4-bae7-413c8b317eb6)
2.	Based on available data, there seems to be a positive correlation between average heart rate and average sleep minutes per day. 
3.	There are a few outliers based on the Quartile 1 (25th percentile) and Quartile 3 (75th percentile) for both average heart rate and average sleep minutes per day.
4.	Average Heart Rate
a.	Quartile 1 (25th percentile): 68.25
b.	Quartile 3 (75th percentile): 81.91
5.	Average Daily Sleep Minutes
a.	Quartile 1 (25th percentile): 203.89
b.	Quartile 3 (75th percentile): 487.74
6.	Outliers
a.	User 27: Average Heart Rate is 65.63, and average daily sleep minutes is 538.51
b.	User 20: Average Heart Rate is 88.11, and average daily sleep minutes is 74.81
c.	User 13: Average Heart Rate is 66.14, and average daily sleep minutes is 535.96

![Low Active and High Active Rates](https://github.com/user-attachments/assets/7af364c7-83c8-409c-b6cd-2af72d4adb44)
![Weight and Average Calories](https://github.com/user-attachments/assets/14cc6246-91bf-4f06-ab2d-f8699a99358f)
2.	Based on the available data, there seems to be no correlation between average weight and average calories burned per day. 

![Weight and Average Daily Intensities](https://github.com/user-attachments/assets/ba85e555-7371-413b-b4f0-a35102863fa9)
2.	Based on available data, there seems to be no correlation between weight and average daily intensity for the Fitbit users. 
![Weight and Average METS](https://github.com/user-attachments/assets/f94f60d9-ad31-484e-9824-e04f581aabde)
Based on the available data, there seems to be a slight positive correlation between weight and average METS per day. 
Average Weight Outliers
a.	25th percentile (Quartile 1): 138.05 
b.	75th percentile (Quartile 3): 202
Average METs Outliers
a.	25th percentile (Quartile 1): 16833.58
b.	75th percentile (Quartile 3): 24256.92
Two notable outliers are: User 24 and User 22. User 24 was an outlier above 75th percentile (Quartile 3) or average weight and below 25th percentile (Quartile 1) for average METs per day. User 22 was an outlier below 25th percentile (Quartile 1) for average weight and above 75th percentile (Quartile 3) for average METs per day. 
