# Kickstarting With Excel

## Overview Of Project
For this project,I am using Kickstarter dataset.I will analize and visualize campaign outcomes column based on their Launch dates and their funding goals.By Analysing and visualizing,i will **"prepare outcomes based on launch date"** chart and **"outcomes based on goals"** chart too.

### Analysis And Challenges

1 **Analysis of outcomes based on lauch date**

* In kickstarter dataset,launch date given in **Unix Timestamps** .so first I changed Unix Timestamps in readable format and make new column,named **Date Created Conversion** with the help of this formula =(((j2/60)/60)/24)+DATE(1970,1,1) .[How to Convert Unix Timestamps to Readable Format](https://courses.bootcampspot.com/courses/779/pages/1-dot-3-3-timing-success?module_item_id=299731)
* Created a new column labeled **Years**.In the Years column,I used the YEAR() function to extract the year from the “Date Created Conversion” column.

* **Challenges :**  According to task,i have to Filter the pivot table based on "Parent Category" and "Years."I have years column but i don't have parent category column.Before making pivot table I splitted the "**Category and subcategory**" column from kickstarter into two distinct column "**Parent category**" and "**Subcategory**".[How to create subcategories from a column](https://courses.bootcampspot.com/courses/779/pages/1-dot-3-1-pivoting-toward-success?module_item_id=299719)


![Created 'Date Created Conversion' column by converting Unix Timestamps into readable formate,created years column from year() function apply on date created conversion column,subcategorized "category and subcategory column into parent category and subcategory](https://user-images.githubusercontent.com/90277142/133908588-193ebc74-6125-4c40-a8b5-6288909ad013.png)

* I Created a pivot table from the KickStarter worksheet and place the pivot table in a new sheet.Label the sheet "**Theater Outcomes by Launch Date.**" I created pivot table,first click on Insert tab and then select pivot table option.
* For filter the pivot table based on "Parent Category" and "Years.I dragged Parent category and years from pivotchart field to filters. Then i dragged Outcomes column from pivotchart field to columns,put ""Date created convertion"" column in rows and Outcomes column into values to know the count of Outcomes.
* Then Filter the column labels to show only "successful," "failed," and "canceled" outcomes. I click arrow that is right side of column that activate the dropdown menu ,First i will deselect the default option "Select all" then choosed only "successful,""failed," and "canceled" outcomes.

**My Pivot Table looks like this:**

![Pivot_Theater Outcomes by Launch Date](https://user-images.githubusercontent.com/90277142/133941184-9a64a997-dd37-4c98-b2ac-a8511584641f.png) 


* Filter the "Parent Category" to show only the data for "theater,I clicked the right side arrow of parent category and selecting the theater from dropdown menu.
* For Sorting the campaign outcomes in descending order so "successful" is first,I put filter on outcome column and choosed Sort Z to A option for descending order.

**My Final pivot table looks like the following:**

![pivot table of theater outcomes](https://user-images.githubusercontent.com/90277142/133909885-d27e8366-fe5a-4fc0-b948-4f6bf68dc6d1.png)

* I created a line chart from the "theater Outcomes by launch date" pivot table to visualize the relationship between outcomes and launch month.For Line chart first i click on    Insert tab then in "Charts option". I got "Insert Line and Area chart". I choosed that one then 2D-Line.Then I got Line Chart. 
* For Adding a title to the line chart,when I clicked on line chat it shows + sign at the right side of chart.I clicked on that sign,it open a small window of "Chart Elements" .I selected Chart Title from that window,it was giving me option to write chart title on Line chart.

![Theater_Outcomes_vs_Launch date chart](https://user-images.githubusercontent.com/90277142/133910375-b351b082-e3fb-4b1e-b620-41b2ffcc63ad.png)

2   **Outcomes Based On Goals Chart**

* In the KickStarter sheet,I created a new sheet and label it "Outcomes Based on Goals."In Outcome based on goals sheet, create the following **columns** to hold the data:
    Goal,Number Successful,Number Failed,Number Canceled,Total Projects,Percentage Successful,Percentage Failed,Percentage Canceled.
* In the “Goal” column,I created the following dollar-amount ranges so projects can be grouped based on their goal amount. Less than 1000, 1000 to 4999, 5000 to 9999, 10000 to 14999, 15000 to 19999, 20000 to 24999, 25000 to 29999, 30000 to 34999, 35000 to 39999, 40000 to 44999, Greater than 50000.
    
    ![Outcomes_based_on_goal-data](https://user-images.githubusercontent.com/90277142/133941435-2865b622-0257-4aa9-8c3b-c84b7582987b.png)

    
* **Challenges:** I used COUNTIFS() function first time so it was challenging and even i was using COUNTIFS() function on "Outcome Based On Goals sheet" and getting Criteria Range from kickstarter sheet.I used "SHOW HINT" to learn abount COUNTIFS() Function.And I also watched some video from youtube learn it how to use this Function.[COUNTIFS Function](https://www.youtube.com/watch?v=Ihkgs7T3Do0)
* In COUNTIFS() function we first take Criteria range for a column of interest and the criteria to filter data from that column and I Used COUNTIFS() functions to populate the "Number Successful," "Number Failed," and "Number Canceled" columns by filtering on the Kickstarter "outcome" column, on the "goal" amount column using the ranges created ahead, and on the "Subcategory" column using "plays" as the criteria.For this I get three Criteria Range,one from Kickstarter sheet,i took outcomes column range that was F2:F4115,and put criteria should be Successful and second goals column range(D2:D4115) from kickstarter sheet and put criteria that given in "Outcome Based On Goals sheet" then last from kickstarter sheet, took subcatory column range(p2:p4115) and put criteria as "paly" only.

=COUNTIFS(Kickstarter!F2:F4115,"=successful",Kickstarter!D2:D4115,"<1000",Kickstarter!P2:P4115,"plays")

=COUNTIFS(Kickstarter!F2:F4115,"=failed",Kickstarter!D2:D4115,"<1000",Kickstarter!P2:P4115,"plays")

=COUNTIFS(Kickstarter!F2:F4115,"=canceled",Kickstarter!D2:D4115,"<1000",Kickstarter!P2:P4115,"plays")

* I changed the Goal amount in the goal column range in everygoal amount row and got "Number Successful," "Number Failed," and "Number Canceled".

* I Used the SUM() function to populate the "Total Projects" column with the number of successful, failed, and canceled projects for each row.In SUM() function I added cell B2,C2,D2 to get total project number.
* For Calculating the percentage of successful, failed, and canceled projects for each row.I divided number_successful,number_failed and number_canceled by total_number to get percentage for each row.
* With the help of Outcome Based On Goals sheet dataset i created a line chart titled "Outcomes Based on Goal" to visualize the relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, or canceled projects on the y-axis.

**My line chart looks like the following:** 

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/90277142/133913699-9f932948-48c4-4a69-b6a3-b7b1fa21f0b3.png)

#### Results:
* **Theater Outcomes by Launch Date:**
      1 For "Theater Outcomes by Launch Date" sheet and chart,I wanted “Date Created Conversion” column that I created from "launched at" column.I converted "launched at" Unix timestamps data into readable format.Then i created one new column name "Years" with the help of Year() Function on “Date Created Conversion” column data.
      2 I Subcategorized the "Category and Subcatory" column into two distict column,Parent category and Subcategory. Because I wanted parent category column for filtering data in pivot table and make chart.
 
* **Outcomes based on Goals:**
      For "Outcomes based on Goals" chart I need number of successful,number of failed and number of canceled outcomes on the goals using the goal ranges and on the "Subcategory" column using "plays" as the criteria for each row.I calculated "Number Successful," "Number Failed," and "Number Canceled" by using COUNTIFS() function.Then i calculated total project by adding "Number Successful," "Number Failed," and "Number Canceled" for each row by using SUM() Function. Then i calculated percentage of successful, failed, and canceled projects for each row.I divided number_successful,number_failed and number_canceled by total_number to get percentage for each row. At last I got all data what i wanted to make Outcomes based on Goals Chat.

* **limitations of the dataset**
1. If we change anything in dataset, it is not been reflected in Pivot on it's own. But it has to be refereshed to reflect the changes.
2. Excel limits visibility of dataset when we have more columns and Keeping track of multiple sheets is challenging. 
* **Recommendation for additional tables or graphs**
     A line graph has the advantage of showing changes over time,So we can See the trend of Outcomes.Other graphs, such as pie charts, are used to show components of one whole.if we will use pie chart ,we can show the percentage of Outcomes.



 
 
    
   

