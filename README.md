# Movies-ETL
## Overview
The purpose of this project was to extract important, descriptive data from large, "dirty" files, which will then eventually be transformed, and loaded into a new database for additional analysis (SQL). The project started with 2 sizable data files containing movie data throughout the years. The two datasets were cleaned by accounting for null values, filtering for pertinent data, merging similar columns, using regular expressions to format the data consistently, and much more. Once the two datasets were cleaned and combined, it was loaded into SQL Alchemy to run additional queries and to gain further insights.
## Results
The two large movie datasets contained similar information with differing headings/column names. To consolidate the data, a function was created to rename column names with similar information. This will eliminate unnecessary column names without losing column values and allow for merging later on. In the process of standardizing the columns, a small number of null values were dropped for consistency.
![function](https://github.com/carrotdip/Movies-ETL/blob/4b05ff0996618261b019c4343e8603a6d194db6e/Images/function%20to%20combine%20similar%20columns.png)
Then, a function was created to normalize the budget information utilizing regular expressions. The values were not uniform, thus the function was formed to create a complete and coherent dataset.
![function](https://github.com/carrotdip/Movies-ETL/blob/4b05ff0996618261b019c4343e8603a6d194db6e/Images/function%20to%20normalize%20budget%20column.png)
The release dates of the movies were also in different formats, so another function was constructed to standardize the date formats.
![function](https://github.com/carrotdip/Movies-ETL/blob/4b05ff0996618261b019c4343e8603a6d194db6e/Images/function%20to%20normalize%20dates.png)
Finally, once all the column names and values were properly formatted, the two datasets were merged. In the case that both datasets contained the same information (i.e. budget), the dataset with the least amount of nulls was used and the other dropped. 
![merge](https://github.com/carrotdip/Movies-ETL/blob/822ba166f50a33c3b99a13e04e67728860133580/Images/merge%20dataframes%20and%20load%20into%20SQL.png)
Once the two datasets were merged, the table was imported into SQL for additional queries.
![query1](https://github.com/carrotdip/Movies-ETL/blob/4b05ff0996618261b019c4343e8603a6d194db6e/Images/movies_query.png)
![query2](https://github.com/carrotdip/Movies-ETL/blob/4b05ff0996618261b019c4343e8603a6d194db6e/Images/ratings_query.png)
