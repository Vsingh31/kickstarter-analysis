# Kickstarting With Excel
## Overview Of Project
For this project,I am using Kickstarter dataset.I will analize and visualize campaign outcomes column based on their Launch dates and their funding goals.By Analysing and visualizing,i will prepare outcomes based on launch date chart and outcomes based on goals chart too.
### Analysis And Challenges
**Analysis of outcomes based on lauch date**
* In kickstarter dataset,launch date given in **Unix Timestamps** .so first I changed Unix Timestamps in readable format and make new column,named **Date Created Conversion** with the help of this formula =(((j2/60)/60)/24)+DATE(1970,1,1) .
created a new column labeled **Years**.In the Years column,I used the YEAR() function to extract the year from the “Date Created Conversion” column.


![Created 'Date Created Conversion' column by converting Unix Timestamps into readable formate](https://user-images.githubusercontent.com/90277142/133906780-2d87a47d-3ff3-4a7c-bc9c-e4387072e3ee.png)


I created pivot table in new sheet and Label the sheet **Theater Outcomes by Launch Date.
**Challenges**According to task,i have to Filter the pivot table based on "Parent Category" and "Years."I have years column but i don't have parent category column.Before making pivot table I splitted the "**Category and subcategory**"column from kickstarter into two distinct column "**Parent category**" and "**Subcategory**".[How to create subcategories from a column](https://courses.bootcampspot.com/courses/779/pages/1-dot-3-1-pivoting-toward-success?module_item_id=299719)
