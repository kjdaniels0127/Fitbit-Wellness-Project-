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


**Data Processing Stage** 

1. To start processing the data, I opened up the csv files. I then tried to transfer the csv files to Google Big Query
2. I came across some problems in the data transfer. Down below I’ll show you the issue and the solution to that problem

- Fitbit datasets 04.2016-05.2016

|     Dataset Name                       |     Dataset Status      |     Problems                                                                                       |     Solutions                                                                                                                                                  |
|----------------------------------------|-------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     heartrate_seconds_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitCSV.com to split the file into 8   separate files and (2) Change the date/hour format from   "MM/DD/YYYY" to a format of "YYYY/MM/DD"    |
|     hourlycalories_merged              |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     hourlyintensities_merged           |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     hourlysteps_merged                 |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesCalroiesNarrow_merged       |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minutesIntensitiesNarrow_merged    |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minutesMETSNarrow_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minuteSleep_merged                 |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minuteStepsNarrow_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     weightloginfo_merged               |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesCalroiesWide_merged         |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesIntensitiesWide_merged      |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesStepWide_merged             |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     sleepday_merged                    |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |

- Fitbit Datasets 03.2016-04.2016

|     Dataset Name                       |     Dataset Status      |     Problems                                                                                       |     Solutions                                                                                                                                                  |
|----------------------------------------|-------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     heartrate_seconds_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitCSV.com to split the file into 8   separate files and (2) Change the date/hour format from   "MM/DD/YYYY" to a format of "YYYY/MM/DD"    |
|     hourlycalories_merged              |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     hourlyintensities_merged           |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     hourlysteps_merged                 |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesCalroiesNarrow_merged       |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minutesIntensitiesNarrow_merged    |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minutesMETSNarrow_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     minuteSleep_merged                 |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minuteStepsNarrow_merged           |     Loaded Into SQL     |     Too much data for an Excel workbook. Incomplete dataset   and Problems with the date format    |     (1) Utilized splitcsv.com to split the Excel file into 4   workbooks (2) Change the date/hour format from "MM/DD/YYYY" to a   format of "YYYY/MM/DD"       |
|     weightloginfo_merged               |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesCalroiesWide_merged         |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesIntensitiesWide_merged      |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     minutesStepWide_merged             |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |
|     sleepday_merged                    |     Loaded Into SQL     |     Problems with the date format                                                                  |     Change the date/hour format from "MM/DD/YYYY"   to a format of "YYYY/MM/DD"                                                                                |

**Statistical Summary Tables Based on Data Analysis**

1. These tables utilized these statistical metrics of Minimum, Quartile 1, Average, Quartile 3, and Maximum.

2. Calories

|     Unique User IDs    |     min_calories_total    |     avg_calories_total    |     max_calories_total    |     quartile_1_calories    |     quartile_3_calories    |
|------------------------|---------------------------|---------------------------|---------------------------|----------------------------|----------------------------|
|     User 4             |     42                    |     54.29                 |     219                   |     42                     |     55.5                   |
|     User 13            |     47                    |     61.66                 |     143                   |     48                     |     67                     |
|     User 22            |     47                    |     81.08                 |     304                   |     50                     |     93.25                  |
|     User 6             |     50                    |     58.67                 |     155                   |     50                     |     59                     |
|     User 28            |     52                    |     79.88                 |     466                   |     53                     |     97                     |
|     User 11            |     54                    |     92.12                 |     332                   |     55                     |     117                    |
|     User 27            |     55                    |     75.23                 |     273                   |     55                     |     82                     |
|     User 34            |     55                    |     61.24                 |     186                   |     55                     |     55                     |
|     User 7             |     56                    |     74.88                 |     276                   |     56                     |     87.75                  |
|     User 15            |     56                    |     62.71                 |     191                   |     56                     |     56                     |
|     User 10            |     56                    |     80.17                 |     278                   |     57                     |     91                     |
|     User 26            |     56                    |     89.2                  |     378                   |     58                     |     103                    |
|     User 32            |     59                    |     62.63                 |     294                   |     60                     |     60                     |
|     User 25            |     61                    |     89.48                 |     233                   |     61                     |     107                    |
|     User 17            |     62                    |     108.86                |     538                   |     62                     |     127                    |
|     User 1             |     62                    |     94.75                 |     473                   |     63                     |     120                    |
|     User 20            |     65                    |     111.03                |     501                   |     65                     |     129                    |
|     User 2             |     68                    |     97.55                 |     518                   |     68                     |     104.25                 |
|     User 9             |     69                    |     93.04                 |     361                   |     70                     |     106                    |
|     User 3             |     70                    |     80.7                  |     248                   |     70                     |     75                     |
|     User 14            |     73                    |     124.84                |     636                   |     73                     |     121                    |
|     User 33            |     73                    |     145.99                |     933                   |     74                     |     154                    |
|     User 18            |     74                    |     80.88                 |     330                   |     74                     |     74                     |
|     User 31            |     76                    |     77.56                 |     392                   |     76                     |     76                     |
|     User 30            |     77                    |     111.88                |     442                   |     77                     |     115                    |
|     User 29            |     77                    |     145.86                |     632                   |     79                     |     170.75                 |
|     User 8             |     80                    |     93.33                 |     160                   |     80                     |     80                     |
|     User 19            |     83                    |     112.52                |     442                   |     83                     |     126                    |
|     User 24            |     83                    |     109.39                |     534                   |     84                     |     106                    |
|     User 5             |     84                    |     96.14                 |     302                   |     84                     |     97                     |
|     User 23            |     84                    |     123.55                |     334                   |     85                     |     149.75                 |
|     User 12            |     83                    |     126.72                |     458                   |     86                     |     140.25                 |
|     User 21            |     86                    |     112                   |     599                   |     86                     |     122                    |
|     User 16            |     90                    |     141.7                 |     669                   |     95                     |     145.75                 |
|     User 4             |     52                    |     1513.67               |     1760                  |     1484.5                 |     1632.25                |
|     User 13            |     1141                  |     1540.65               |     1926                  |     1410                   |     1662.5                 |
|     User 10            |     1237                  |     1933.1                |     2124                  |     1908                   |     2047.25                |
|     User 34            |     1125                  |     1724.16               |     2124                  |     1621.5                 |     1865                   |
|     User 15            |     665                   |     1573.48               |     2130                  |     1347                   |     1803.5                 |
|     User 22            |     0                     |     1816.42               |     2159                  |     1787                   |     1954                   |
|     User 32            |     0                     |     1788                  |     2218                  |     1734                   |     1992                   |
|     User 28            |     1431                  |     1916.97               |     2241                  |     1880                   |     1993                   |
|     User 18            |     1527                  |     1973.75               |     2306                  |     1713.75                |     2291                   |
|     User 27            |     741                   |     1875.68               |     2335                  |     1695.5                 |     2110.5                 |
|     User 9             |     1212                  |     2186.19               |     2499                  |     2116.5                 |     2313.5                 |
|     User 25            |     257                   |     2037.68               |     2530                  |     1885                   |     2268                   |
|     User 11            |     928                   |     1982.03               |     2571                  |     1852.5                 |     2167.5                 |
|     User 24            |     1383                  |     2172.81               |     2638                  |     2063                   |     2331                   |
|     User 7             |     1452                  |     2033.26               |     2666                  |     1899                   |     2152                   |
|     User 26            |     403                   |     2043.44               |     2670                  |     1944.5                 |     2197                   |
|     User 6             |     1002                  |     1483.35               |     2690                  |     1381.5                 |     1525.5                 |
|     User 2             |     1199                  |     2566.35               |     2997                  |     2489.5                 |     2790.5                 |
|     User 3             |     57                    |     1962.31               |     3101                  |     1688                   |     2067                   |
|     User 17            |     1848                  |     2509.97               |     3158                  |     2385                   |     2720.5                 |
|     User 20            |     120                   |     2544                  |     3180                  |     2308.75                |     2922                   |
|     User 21            |     0                     |     2599.62               |     3327                  |     2664                   |     2806                   |
|     User 5             |     0                     |     2732.03               |     3513                  |     2621.5                 |     2945.5                 |
|     User 14            |     1505                  |     2945.81               |     3589                  |     2827.5                 |     3199.5                 |
|     User 23            |     1240                  |     2965.55               |     3691                  |     2877.5                 |     3155                   |
|     User 30            |     1032                  |     2131.77               |     3727                  |     1841                   |     2379.75                |
|     User 12            |     1276                  |     2811.3                |     3846                  |     2491                   |     3180                   |
|     User 19            |     1120                  |     2385.81               |     3879                  |     1980                   |     2877                   |
|     User 35            |     1623                  |     3093.87               |     4022                  |     2962                   |     3278.5                 |
|     User 16            |     1976                  |     3436.58               |     4236                  |     2945                   |     3787.5                 |
|     User 33            |     1849                  |     3420.26               |     4547                  |     2853.5                 |     3820                   |
|     User 29            |     1665                  |     3359.63               |     4552                  |     3006.5                 |     3964                   |
|     User 1             |     1248                  |     2261.14               |     4900                  |     1868.75                |     2564                   |
4. Heart Rate

|     User ID #    |     min_heart_rate_by_id    |     avg_heart_rate_by_id    |     max_heart_rate_by_id    |     quartile_1_heart_rate_by_id    |     quartile_3_heart_rate_by_id    |
|------------------|-----------------------------|-----------------------------|-----------------------------|------------------------------------|------------------------------------|
|     User 29      |     37.00                   |     64.39                   |     174.50                  |     52.60                          |     67.92                          |
|     User 17      |     39.00                   |     79.59                   |     202.00                  |     67.84                          |     87.45                          |
|     User 3       |     44.00                   |     73.10                   |     139.71                  |     64.60                          |     78.79                          |
|     User 19      |     47.50                   |     81.85                   |     191.00                  |     69.60                          |     92.22                          |
|     User 33      |     47.00                   |     76.63                   |     177.00                  |     63.80                          |     80.90                          |
|     User 27      |     47.00                   |     65.38                   |     157.00                  |     59.20                          |     68.22                          |
|     User 11      |     49.00                   |     74.52                   |     173.00                  |     65.10                          |     80.67                          |
|     User 31      |     51.80                   |     82.87                   |     130.17                  |     77.54                          |     87.17                          |
|     User 26      |     51.00                   |     74.45                   |     187.00                  |     65.43                          |     79.50                          |
|     User 1       |     52.00                   |     82.20                   |     180.00                  |     71.75                          |     92.05                          |
|     User 7       |     46.00                   |     78.63                   |     197.00                  |     70.50                          |     85.25                          |
|     User 20      |     55.00                   |     88.79                   |     160.00                  |     78.70                          |     97.69                          |
|     User 13      |     59.50                   |     79.33                   |     122.00                  |     72.98                          |     86.63                          |
|     User 30      |     57.00                   |     93.10                   |     177.00                  |     79.25                          |     106.50                         |
|     User 35      |     41.00                   |     63.99                   |     175.00                  |     56.00                          |     69.00                          
5. Hourly Intensities

|     Unique User IDs    |     min_intensity    |     avg_intensity    |     max_intensity    |     quartile_1_intensities    |     quartile_3_intensities    |
|------------------------|----------------------|----------------------|----------------------|-------------------------------|-------------------------------|
|     User 32            |     0                |     5.25             |     149              |     0                         |     4.75                      |
|     User 15            |     0                |     4.065            |     71               |     0                         |     2                         |
|     User 31            |     0                |     0.68             |     108              |     0                         |     0                         |
|     User 18            |     0                |     3.675            |     117              |     0                         |     4                         |
|     User 34            |     0                |     5.905            |     67               |     0                         |     8                         |
|     User 8             |     0                |     10               |     60               |     0                         |     0                         |
|     User 3             |     0                |     3.845            |     84               |     0                         |     2.5                       |
|     User 5             |     0                |     6.58             |     178              |     0                         |     6.5                       |
|     User 6             |     0                |     6.855            |     169              |     0                         |     8                         |
|     User 24            |     0                |     5.44             |     174              |     0                         |     4                         |
|     User 19            |     0                |     5.55             |     126              |     0                         |     4.5                       |
|     User 30            |     0                |     7.375            |     144              |     0                         |     4.5                       |
|     User 4             |     0                |     11.705           |     147              |     0                         |     13                        |
|     User 2             |     0                |     11.36            |     166              |     0                         |     11.5                      |
|     User 27            |     0                |     11.585           |     144              |     0                         |     16                        |
|     User 21            |     0                |     10.065           |     143              |     0                         |     17.5                      |
|     User 7             |     0                |     11.74            |     123              |     0                         |     19                        |
|     User 9             |     0                |     9.825            |     137              |     0                         |     15.375                    |
|     User 14            |     0                |     18.125           |     180              |     0                         |     17.75                     |
|     User 23            |     0                |     12.585           |     119              |     0                         |     19.75                     |
|     User 33            |     0                |     19.15            |     180              |     0                         |     21                        |
|     User 26            |     0                |     14.745           |     153              |     0                         |     20.5                      |
|     User 25            |     0                |     12.26            |     87               |     0                         |     19.625                    |
|     User 20            |     0                |     17.61            |     174              |     0                         |     24                        |
|     User 28            |     0                |     14.845           |     168              |     0                         |     24                        |
|     User 17            |     0                |     17.775           |     169              |     0                         |     24.5                      |
|     User 1             |     0                |     13.12            |     149              |     0                         |     24.5                      |
|     User 29            |     0                |     20.31            |     180              |     0                         |     24.125                    |
|     User 11            |     0                |     16.64            |     159              |     0                         |     26                        |
|     User 13            |     0                |     9.825            |     56               |     0.5                       |     15                        |
|     User 16            |     0                |     14.34            |     165              |     1.5                       |     13                        |
|     User 12            |     0                |     12.675           |     130              |     0.5                       |     14.5                      |
|     User 10            |     0                |     14.7             |     105              |     1                         |     23.625                    |
|     User 22            |     0                |     16.705           |     159              |     1                         |     22.5                      |
|     User 35            |     0                |     14.31            |     154              |     0                         |     17                        |
7. Minutes By METs         

10. Total Distance By ID 

|     Unique Username    |     min_distance_by_id    |     avg_distance_by_id    |     max_distance_by_id    |     quartile_1_total_by_id    |     quartile_3_total_by_id    |
|------------------------|---------------------------|---------------------------|---------------------------|-------------------------------|-------------------------------|
|     User 23            |     0.00                  |     6.71                  |     12.27                 |     5.495                     |     7.825                     |
|     User 30            |     0.00                  |     2.90                  |     10.03                 |     0.565                     |     4.975                     |
|     User 28            |     0.00                  |     4.79                  |     9.56                  |     3.99                      |     5.71                      |
|     User 21            |     0.00                  |     2.75                  |     7.44                  |     2.105                     |     2.7                       |
|     User 25            |     0.00                  |     5.08                  |     9.49                  |     4.15                      |     6.31                      |
|     User 18            |     0.00                  |     2.13                  |     6.23                  |     1.105                     |     3.11                      |
|     User 32            |     0.00                  |     3.18                  |     9.15                  |     1.455                     |     4.405                     |
|     User 34            |     0.00                  |     2.66                  |     7.67                  |     1.145                     |     3.74                      |
|     User 15            |     0.00                  |     2.06                  |     5.32                  |     0                         |     3.375                     |
|     User 31            |     0.00                  |     1.07                  |     7.51                  |     0                         |     0.13                      |
|     User 1             |     0.00                  |     5.79                  |     15.01                 |     3.405                     |     7.63                      |
|     User 35            |     0.00                  |     4.20                  |     17.54                 |     3.78                      |     4.715                     |
|     User 26            |     0.00                  |     6.44                  |     15.08                 |     5.34                      |     6.98                      |
|     User 8             |     0.00                  |     0.60                  |     3.22                  |     0                         |     0.4                       |
|     User 19            |     0.00                  |     2.89                  |     8.99                  |     1.535                     |     4.175                     |
|     User 3             |     0.00                  |     1.59                  |     5.41                  |     0.39                      |     2.265                     |
|     User 2             |     0.00                  |     5.24                  |     10.82                 |     3.35                      |     6.85                      |
|     User 24            |     0.00                  |     1.07                  |     3.92                  |     0.38                      |     1.535                     |
|     User 22            |     0.00                  |     7.71                  |     12.21                 |     6.95                      |     8.58                      |
|     User 9             |     0.19                  |     3.08                  |     6.11                  |     2.165                     |     4.125                     |
|     User 14            |     0.21                  |     11.53                 |     20.14                 |     9.485                     |     13.605                    |
|     User 6             |     0.53                  |     3.33                  |     28.03                 |     1.355                     |     3.975                     |
|     User 4             |     0.50                  |     6.67                  |     11.05                 |     4.54                      |     8.495                     |
|     User 13            |     0.16                  |     2.78                  |     7.71                  |     1.845                     |     3.475                     |
|     User 7             |     0.83                  |     4.45                  |     9.08                  |     3.605                     |     5.42                      |
|     User 12            |     0.89                  |     6.03                  |     14.71                 |     3.3                       |     8.14                      |
|     User 27            |     0.43                  |     5.55                  |     11.12                 |     2.77                      |     7.87                      |
|     User 5             |     0.00                  |     4.00                  |     11.83                 |     2.705                     |     4.9                       |
|     User 16            |     1.69                  |     6.68                  |     12.85                 |     3.655                     |     9.035                     |
|     User 33            |     1.78                  |     13.65                 |     27.53                 |     8.145                     |     19.35                     |
|     User 29            |     0.00                  |     6.33                  |     11.78                 |     4.32                      |     8.035                     |
|     User 10            |     2.10                  |     4.47                  |     6.63                  |     3.535                     |     5.365                     |
|     User 17            |     2.31                  |     8.43                  |     13.83                 |     7.125                     |     10.05                     |
|     User 11            |     1.03                  |     7.62                  |     13.24                 |     6.085                     |     9.01                      |
|     User 20            |     0.00                  |     8.44                  |     14.30                 |     6.315                     |     10.38                     |





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
