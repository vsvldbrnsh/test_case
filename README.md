#  Exploratory Data Analysis
### 1 Introduction
This is an explorator data analysis of the Iowa alcohol dataset. The dataset has over 17M  observation and divided into 10 separate files. Files were downloaded from Bigquery public data storage and placed into storage bucket (Google Cloud). According to limitations imposed by my PC performance i decided to work with a part of data, not with all of 17M records.For EDA were used only 4836011 rows
Files in the repository:
  - Alco.ipynb
  - README.md

### 2 Preparations
Libraries: pandas, matplotlib.pyplot, seaborn,os
Fields:
  - Int64Index: 4836011 entries, 0 to 9672020
  - Data columns (total 24 columns):
  - nvoice_and_item_number:    object
  - date:                       object
  - store_number:               int64
  - store_name:                 object
  - address:                    object
  - city:                       object
  - zip_code:                   object
  - store_location:             object
  - county_number:              float64
  - county:                     object
  - category:                   float64
  - category_name:              object
  - vendor_number:              float64
  - vendor_name:                object
  - item_number:                object
  - item_description:           object
  - pack:                       int64
  - bottle_volume_ml:           int64
  - state_bottle_cost:          float64
  - state_bottle_retail:        float64
  - bottles_sold:               int64
  - sale_dollars:               float64
  - volume_sold_liters:         float64
  - volume_sold_gallons:        float64
 
### 3 Overview: Gaining a basic understanding of our dataset
	A few things:
	There are some useless variables we could drop ('invoice_and_item_number','pack','volume_sold_gallons').
	There isn’t a "brand" column and "type of drink" column.

### 4.Make new features(Extract them from "date" filed previously converted it to datEtime format):
  - WEEKDAY
  - MOTHDAY
  - YEAR
  - MONTH
  - MARGIN (extra feature that counts trade margin revenue per deal(state_bottle_retail-state_bottle_cost)

### 5.Exploring data for missing values.
### 6.Make fast summary(helicopter view) 
### 7.Basic Visualizations
### 8.Brand Exploration
### Key Findings: 

 > 1.On the average every deal:
  - costs 134$
  - sells 10 bottles
  - sells 9 liters
  - have 4.9$ margin per bottle
  - monday(0) is the day with the higest revenue flow. After Thursday(3) the amount of sales declines sharply and nearly stoppes at the end of the week.
  - "year" and "month" charts show permanent increase of sales from year-to-year and from month-to-month respectively. However according to "month" chart, 10th and 12th monthes include the highest sales peaks.

> 2.At the beginning of the period the highest sales flow was on Monday. But to the end of the period this difference became flatter (from Monday to Thursday). No sales during saturday and sunday.

> 3."Canadian whiskies" category is the most popular. Something had happened between 2015-2016 yrs and category structure changed. For instance "VODKA 80 PROOF" was replaced by the "American Vodkas".
Categories had dissapeared since 2016:
  - "vodka 80 proof"
  - "vodka flavored"
  - "tequila"
  - "imported vodka"
  - "puerto rico & virgin islands rum"
  - "american cocktails"
  - "imported vodka - misc"
  - "misc. imported cordials & liqueurs"
  - "american grape brandies"

Categories had broken into the market:
  - "american flavored vodka"
  - "flavored rum"
  - "tennessee whiskies"
  - "american dry gins"
  - "american flavored vodka"

> 4.These categories are the market drivers that generate the biggest part of sales revenue:
  - "canadian whiskies"
  - "spiced rum"
  - "american vodkas"
  - "vodka 80 proof"
  - "straight bourbon whiskies"
  - "whiskey liqueur"
  - "tennessee whiskies"
  - "imported vodka"

5. Growing and Decreasing drinks types:
  - bourbone,gin,whiskey becomes more popular YTY
  - vodka,brandy,liqueur,margarita,tequila looses their popularity YTY


> I took 9 top brands by "sale_dollars":
  - Captain: whiskey
  - Crown: whiskey
  - Fireball: whiskey
  - Black: whiskey
  - Jack: whiskey
  - Smirnoff: vodka
  - Titos: vodka
  - Jose: margarita

> 6.Brand sales$ per Year
  - Captain,Smirnoff,Jack,Absolute, Black are brands that have already gained stable market share. They are at the top and have a little growth in "sale_dollars" YTY.
  - Titos,Fireball,Crown and Jose are growing extremely from year to year. 

> 7.Brand sales by month
  - Captain:biggest purchases in october and december
  - Smirnoff:the highest peak in may and june
  - Crown:at the same level all the year except october and december(extremely high)
  - Jose:the highest level only in april, then purchases decreasing
  - Jack:two peaks in october and december
  - Titos:two peaks in june and september
  - Fireball:growing all the time from january to decembre
  - Black:february,may and october 

