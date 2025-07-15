# PROJECT OVERVIEW

Quantium Retail Analytics 
Project:  Chips Product Insights.
- This project focuses on uncovering valuable insights into customer segments and purchasing behavior related to chips products. The analysis is based on two CSV datasets: Purchase Behaviour and Transaction Data.
The primary goal is to identify individual customers who purchase chips and analyze their behaviour based on factors such as brand pricing, pack size, customer lifestage, and preferences. Using Python for data exploration, visualization, and hypothesis testing, this project aims to help retailers better understand sales trends and make informed decisions. The objective is to deliver actionable insights to improve retail management strategies and understand customer segments and purchasing patterns more effectively. 

#### Dataset Summary
- 'LYLTY_CARD_NBR': loyalty card number 
- 'LIFESTAGE': The various life stages of the customers
- 'PREMIUM_CUSTOMER': The ranking column of customer segment
- 'DATE': The daily records date
- 'STORE_NBR': The individual store numbers
- 'TXN_ID': The unique transaction ID
- 'PROD_NBR': The unique product numbers
- 'PROD_NAME': The names of products in the store
- 'PROD_QTY': The quantity of products purchased per customer in a day
- 'TOT_SALES': The total sales of product(s) to an individual customer

###### CONFIGURATION
- Necessary Libraries: The analysis includes python libraries such as pandas, numpy, seaborn,matplotlib, plotly, scipy, sklearn for data manipulation, visualisation, hypothesis and predictive analysis.


# UNDERSTANDING CHIPS SALES DYNAMICS

* Why do customers with higher number of loyalty card numbers tend to purchase more product?. When customers are giving loyalty card numbers, it encourage them to buy more of products and to stay as permanent customers. 
* What are the possible causes of chips sales drop during February, August and May? This maybe due to the events of not opening the stores early for sales during that period.
* Why is there a significant increase in sales during December? During the month of December is mostly a holiday period; hence, retailers can boost sales of low-sales chips product brands like french, woolworths, burger, cheetos, sunbites, css, and cheezels by doing promotions.
* Which store numbers have higher sales as well as store numbers with lower sales? From the above analysis, it shows that store numbers such as [4, 26, 40, 58, 88, 165, 199, 203, 226 and 237] have higher total chips product sales from 2018 to 2019. On the other hand, store numbers [11, 42, 92, 117, 139, 140, 146, 158, 159, 177, 192, 198, 206, 252, 263, 267] have lower chips product sales from 2018 to 2019. Therefore, implementing A/B testing for reshuffling some managers is recommended.
* Which pack size of chips brand do customers prefer most as well as those they prefer less? Customers prefer chips products with 150g and 175g pack sizes and purchase less of chips products with 70g, 90g, 125g, 135g, 160g, 180g, 190g, 200g, 210g, 220g, 250g, 270g and 380g pack sizes. This will help retailers identify the particular pack size customers prefers most in order to maintain and improve sales.
* How many quantities of chips products do customers mostly purchase? Customers mostly purchase two quantities of chips products, followed by one quantity, and less for the rest of the quantities.
* Which brand of chips products do customers prefer most? Customers prefer kettle, smiths, doritos and pringles chips brand, and less of french,woolworths,burger,cheetos,sunbites, css, and cheezels chips due to their low average unit price(low quality). 
* Why do OLDER SINGLES/COUPLES purchases much of the chips products? This maybe of their high population, so they tend to purchase more goods, thereby increasing sales. Hence, targeting them will improve sales.
* Why do most customers purchase more of the highly priced chips product? This is because of the higher quality of chips product, thereby increasing the purchasing experience for highly priced chips. However, very few of the low priced products are purchased due to its low quality.
* Which customers purchases much of the low-priced chips products? Most of the OLDER FAMILIES falls under the budget category due to the larger family, where expenses are widely distributed. Hence, they tend to buy chips products with cheaper prices.
* Which category of customers purchases highly priced chips products? OLDER SINGLES/COUPLES. This is because most of the older singles have fewer family duties, so they tend to purchase any product of their choice.

# EXPLORATORY DATA ANALYSIS, WRANGLING AND DATA VISUALISATION

 - Using Python libraries like pandas for cleaning missing values, dropping duplicates, merging the two dataframes, and describing data for statistical summaries such as the mean, standard deviation, frequency, minimum, and maximum values of the data. It also helps in datatype conversion and identifying the shape of the data.  
 - I also used other libraries like numpy for array manipulation, and scipy for t-test hypothesis on independent variables.  
 - Libraries such as Seaborn and Matplotlib helped in identifying outliers using histograms, boxplots, and scatter plots for visualizing relationships between variable values.
- Plotly express, helped create an interactive plots for time series analysis and identifying partterns in customer segments and purchasing behaviour.

- Univariate Analysis  
    - The visualization of categorical variables using bar plots and the describe() method to identify the frequency distribution of each variable.  
    - For numerical variables, plots such as histograms helped in identifying and eliminating outliers to improve data quality and reduce bias in training models.  
    - Line plots were used to determine the temporal trends of continuous values such as sales.  

- Bivariate Analysis  
    - Using plots such as heatmaps to identify the correlation between numerical variables in the data.
    - Using grouped bar plots to identify the relationship between categorical variables and their frequencies.  
    - Additionally, crosstab helps in identifying the frequency of relationships between two variables.
 
  # FEATURE ENGINEERING

  - The PROD_NAME feature was broken down to derive two additional features: PACK_SIZE and the BRAND name of the chips product. This helped us better understand the type and size of chips products we were working with. Additionally, a new feature CHIPS was derived from the PROD_NAME column to help identify chips products and classify the product names into chips and non-chips products, since our interest lies only in chips.

- Features such as STORE_NBR and LYLTY_CARD_NBR were dropped, as both showed a perfect positive correlation with the PROD_NBR column. This was done to prevent redundancy during model training.

Feature Types:

- Datetime Feature:  
    - Extracted additional information such as MONTH feature for monthly trends in sales. Also I broke down the DATE feature to analyse daily, monthly and yearly trends of chips sales.

- Numerical Features:  
    - LYLTY_CARD_NBR  
    - STORE_NBR  
    - TXN_ID  
    - PROD_NBR  
    - PROD_QTY  
    - PACK_SIZE  
    - CHIPS
    - MONTH

- Categorical Features:  
    - LIFESTAGE  
    - PREMIUM_CUSTOMER  
    - PROD_NAME  
    - BRAND

These features provide comprehensive information for analyzing sales trends, customer segments, and purchasing behaviour.


# MODEL TRAINING

I built a predictive model using a pipeline to streamline the training workflow, incorporating a OneHotEncoder for preprocessing categorical variables. I trained four different models, all of which performed above 90%, with the RandomForestRegressor standing out by achieving approximately 100% accuracy. Model performance was evaluated using metrics such as Mean Squared Error (MSE), Mean Absolute Error (MAE), and R² Score.

# RECOMMENDATIONS AND SOLUTION

  - A/B testing on store management:  
  Conduct A/B testing to evaluate the impact of reshuffling store managers versus maintaining existing ones. Monitor the variation in total sales to assess management effectiveness.
- From the above analysis, it indicates that customers with high number of loyalty cards tend to purchase more of the products. Hence retailers should encourage giving out more loyalty card number to encourage customer purchasing experience to boost sales. 
- Promote low selling products in peak months:  
  Increase promotions for low performing chips products such as  french, woolworths, burger, cheetos, sunbites, css, and cheezels during high consumption periods like December to boost visibility and sales.

- Optimize store operations during key periods:  
  Improve store management strategies during February, May, and August, when sales may dip, to enhance customer experience and drive purchases.

- A/B testing for product placement:  
  Test various store locations for low-performing chip brands to determine optimal shelf positioning that maximizes customer visibility and sales.

- Boost brand awareness through advertising:  
  Increase advertisement efforts for chips brands to attract new customers and retain existing ones through strategic campaigns.

- Target specific lifestage segments:
- Focus on Older Singles/Couples, Retirees, Older Families, and Young Families in that order who show strong purchasing behavior. Encourage them to try low-selling chips to increase sales across product lines.

- Segment based promotions:  
  Since most customers fall under the Mainstream segment, targeting additional groups like Midage Singles/Couoles and Young Singles/Couples can significantly expand the customer base and boost sales.

- Highlight select chip brands:  
  Actively promote well received brands such as kettle, smiths, doritos and pringles, which have the potential to enhance customer buying experience.

- Daily inventory and shelf optimization:  
  Implement regular checks on product placement and shelf arrangement to ensure chips products are always visible and accessible to customers.

- Monitor external factors:  
  Keep track of external influences such as economic fluctuations, climate changes, and seasonal temperature shifts. These can affect customer behavior. Retailers should strategically adjust pricing and promotions based on these factors to maintain customer engagement and improve overall purchasing experience.


                                              <--- RUBYFATH --->
