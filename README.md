# 2020-Big-Contest-Champion-League

## Background

Big Contest is the biggest data analytics competition with real-world problems in South Korea that is held annually.

Our team, data atelier, took the pledge to participate in the champion league track. There, we solved a sales forecasting task for a home shopping company in the country. 

We, unfortunately, didn't get to win the medals, however, we did make it to the finalist, ranking in top 16 out of 500+ participants (Top 3%).

After the competition, our team decided to share our approach & scripts here in the hope that we could be of any help for all the data science enthusiasts out there. 😉



## Problem Description: Sales Prediction for NS SHOP+ Home shopping

NS SHOP+ is a relatively new business model launched in 2015 by NS Home Shopping, which allows consumers to make real-time orders with their own remote controls.

To gain the competitive edge in the higly competitive home shopping market, the company asked for the contestants to suggest the best way to optimize its airing schedule appying ML/DL. 

### Dataset
*Notes: As datasets sharing is strictly forbidden by the competition rules, therefore we won't upload any piece of them.*

Training set - The company's airing schedule and corresponding sales records from Jan 2019 ~ Dec 2019.

Test set for evaluation - The airing schedule for Jun 2020 

Reference data - Audience rating of the NS SHOP+ TV channel (in minutes)

#### Features

- Date: date & time information of the airing; consisted of year, month, date, hour, and time
- Product_Group_Code (a.k.a Mother_Code)
- Product_Group_in_KOR
- Product_Code
- Product_Name
- Price_Per_Unit
- Total_Sales
- Time_Exposed: An amount of time a product was aired and shown to customers. Ususually decided in the airing shcedule planning process.

#### External datasets
After some research on the business context, our team decided to add features from external sources to build a model with better predictive power.

##### Weather data from Korea Meteorological Administration

It is well-known that home shopping sales tends to increase when the weather is not appropriate for outdoor activities. 
To reflect this common sense, we gathered weather data - humidity, temperature, precipitation, etc. - from the Korea Meteorological Administration's website and wrangled them and merged them as wheather features.

##### Shopping Trend data from Naver DataLab

We also wanted to incorporate consumer's interest towards different product as this would affect the sales, hence used search volume data by defferent demographic consumer groups to achieve our goal. 

### Model Evaluation Metrics

MAPE (Mean Absolute Percentage Error) - This was the evaluation metric set in stone by the company

![alt text](https://wikimedia.org/api/rest_v1/media/math/render/svg/5ada3996551e35503a1605edd4e35a26f1215d36)

Additionally, our team also used RMSE (Root Mean Squared Error) when training the model.

## Some Exploratory Data Analysis Findings
1. Kimchi sales peaked in winter season
2. Household goods were sold most on Mondays & Tuesdays
3. The most popular prduct group in the evening time was Cosmetics
4. Regardless of product groups and types, consumers tended to make more last-minute orders rather than bought at first sight
5. Interestingly, audience rating dataset didn't align well with the sales 

etc...
    
    
## Modeling

In terms of model training, time-based splitting in training and validation sets worked better when it comes to model accuracy. Also, this splition method apparently reduced the risk of overfitting. 

Below is the structure of our final prediction model.

![alt text](https://github.com/data-atelier/imgs/blob/a5ba298cf9230a44f54495516bfe96b21ff90903/model_structure.PNG)

## What did we do good?
1. Utilized external sources well which turned out to be effective in predicting sales
2. Split the training & validation set based on time to better reflect the time-sensitive nature of the home shopping business and prevent overfitting
3. Used feature embedding method when dealing with product code feature that helped effectively reduce the feature dimension

## What can we do better next time?
1. Could consider leveraging time series forecast when stacking models

## Python Scripts 
- 
