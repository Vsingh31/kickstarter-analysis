# Kickstarting With Excel
## Overview Of Project
For this project,I am using Kickstarter dataset.I will analize and visualize campaign outcomes column based on their Launch dates and their funding goals.By Analysing and visualizing,i will prepare outcomes based on launch date chart and outcomes based on goals chart too.
### Analysis And Challenges
**Analysis of outcomes based on lauch date**
* In kickstarter dataset,launch date given in **Unix Timestamps** .so first I changed Unix Timestamps in readable format and make new column,named **Date Created Conversion** with the help of this formula =(((j2/60)/60)/24)+DATE(1970,1,1) .
created a new column labeled **Years**.In the Years column,I used the YEAR() function to extract the year from the “Date Created Conversion” column.
"**Challenges :**"  According to task,i have to Filter the pivot table based on "Parent Category" and "Years."I have years column but i don't have parent category column.Before making pivot table I splitted the "**Category and subcategory**" column from kickstarter into two distinct column "**Parent category**" and "**Subcategory**".[How to create subcategories from a column](https://courses.bootcampspot.com/courses/779/pages/1-dot-3-1-pivoting-toward-success?module_item_id=299719)


![Created 'Date Created Conversion' column by converting Unix Timestamps into readable formate,created years column from year() function apply on date created conversion column,subcategorized "category and subcategory column into parent category and subcategory](https://user-images.githubusercontent.com/90277142/133908588-193ebc74-6125-4c40-a8b5-6288909ad013.png)



