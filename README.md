# Analysis of google merch shop

All data used is [there](https://console.cloud.google.com/bigquery?ws=!1m5!1m4!4m3!1sbigquery-public-data!2sga4_obfuscated_sample_ecommerce!3sevents_20210131).
All step-by-step solutions are attached to task numbers

## Tool

BigQuery

## Goals

The main goal of this project is to study the purchase funnel in terms of dates, advertising campaigns and landing pages - it is needed to find the stages of the funnel where visitors drop off. Also, the task is to find the correlation between user engagement and purchase

## [Task 1](https://console.cloud.google.com/bigquery?sq=138619258054:3766fb282115407fac7905386b7a2f43)

   Data preparation. Selection of events for further creation of the funnel:
1. Start a session on the site.
2. Viewing the product.
3. Adding the product to the basket.
4. Start of placing an order.
5. Adding delivery information.
6. Adding payment information.
7. Purchase.
   
## [Task 2](https://console.cloud.google.com/bigquery?sq=138619258054:58612a4680564fe6bdee0c00e11df079)

Сreating a purchase funnel and calculating CR from first visit to all stages of funnel:

1. To viewing the product.
2. To adding the product to the basket.
3. To start of placing an order.
4. To adding delivery information.
5. To adding payment information.
6. To purchase.

   The result are showed for each date, campaign, medium and source.
   
## [Task 3](https://console.cloud.google.com/bigquery?sq=138619258054:cf89c7eb599d447fbac889074635f94f)

Comparison of conversion between different landing pages.
To perform this task, the page path (the path to the page without the domain address and without link parameters) was obtained from page_location in the session start event.
For each unique page path of the beginning of the session, the following metrics were calculated:
1. The number of unique sessions in unique users.
2. Number of purchases.
3. Conversion from the beginning of the session to a purchase.
   
## [Task 4](https://console.cloud.google.com/bigquery?sq=138619258054:377ff30bccab49a7b1864f6bb3ab446e)

Finding the correlation between user engagement and purchases.
For each unique session:
1. Was the user engaged during this session (if session_engaged = '1')
2. Total user activity time during the session (the sum of the engagement_time_msec parameter from each session event)
3. Whether a purchase occurred during the session
   Then the value of the correlation coefficient was calculated:
1. Between engagement and purchase.
2. Between time of engagement and purchase
