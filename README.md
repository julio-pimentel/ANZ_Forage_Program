# Data@ANZ Virtual Internship

I found about Forage when I was looking for internships while doing my master's degree. Forage is an open-access platform connecting students with their company-endorsed Virtual Work Experience Program, such as ANZ, JPMorgan, and KPMG. The project was based on a dataset containing 3 months worth of transactions for 100 hypothetical customers. It includes purchases, recurring transactions, and salary transactions. It is divided into two parts: exploratory data analysis and predictive data analysis. 

## Part 1. Exploratory data analysis
* The dataset has 12,043 rows.
* Transaction period is from 01/08/2018 to 31/10/2018, with a missing value on 16/08/2018.
* The customers are in Australia except for the customer ID CUS-1617121891.
* The purchase transaction values represented 7,717 values of the 12,043 values from the dataset.
* The purchase transaction frequency is concentrated between AU$5 and AU$30.
* The purchase transaction values have 1,158 outliers (above 85% of the sub-data distribution) between AU$47 and AU$7,081.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/histogram%20purchase%20transaction.png)
* The overall transaction frequency is concentrated between AU$0 and AU$40.
* The overall transaction values have 1,807 outliers (above 85% of the-sub data distribution) between AU$114 and AU$8,835.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/histogram%20overall%20transaction.png)
* The transaction volume was analyzed by the hour and weekday.
* Wednesday, Thursday, and Friday are the days with more transaction volume.
* Monday and Tuesday are the days with less transaction volume.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/average%20transaction%20by%20weekday.png)
* The hours 9:00, 11:00, 17:00 are the highest peak of transaction volume.
* Between 0:00 and 8:00 is the lowest peak of transaction volume.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/average%20transaction%20by%20hour.png)

## Part 2. Predictive data analysis
* The customer's monthly salary was calculated by filtering the "PAY/SALARY" attribute from the columns "txn_description".
* It was assumed that the monthly salary did not change in the interval of the dataset.
* 75% of the customers' salary is between AU$576 and AU$2,886.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/histogram%20customer%20salary.png)
* The original variables of the dataset "age" and "state" were selected.
* New attributes were created from the original variables: (1) balance's median, (2) amount's maximum, (3) amount's mean, (4) number of dates with a transaction, (5) number of
the large transaction amount, (6) average week transactions, (7) age intervals (below 20, between 20 and 40, between
40 and 60).
* Each variable was plotted against the customers' monthly salary.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/salary%20vs%20other%20variables.png)
* The selected variables do not have a significant correlation above 0.50, which is not better than making a guess.
* The first linear regression model using all variables has an R 2 of 0.155 and an MSE of 1,634,256.
* Second model using the variables "age", "amount's maximum", "average week transactions", "gender" and "balance’s medium” has a R 2 of 0.129 MSE of 1,684,761.

![](https://github.com/julio-pimentel/ANZ_Forage_Program/blob/main/Plots/correlation.png)

The project was developed in Python using the libraries Pandas, Seaborn, and NumPy. 
