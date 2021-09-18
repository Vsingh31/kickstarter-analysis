# Kickstarting With Excel
## Overview Of Project
For this project,I am using Kickstarter dataset.I will analize and visualize campaign outcomes column based on their Launch dates and their funding goals.By Analysing and visualizing,i will prepare outcomes based on launch date chart and outcomes based on goals chart too.
### Analysis And Challenges
**Analysis of outcomes based on lauch date**
* In kickstarter dataset,launch date given in **Unix Timestamps** .so first I changed Unix Timestamps in readable format and make new column,named **Date Created Conversion** with the help of this formula =(((j2/60)/60)/24)+DATE(1970,1,1) .
![Created 'Date Created Conversion' column by converting Unix Timestamps into readable formate](https://user-images.githubusercontent.com/90277142/133906780-2d87a47d-3ff3-4a7c-bc9c-e4387072e3ee.png)
