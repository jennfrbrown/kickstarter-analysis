# Kickstarting with Excel

## Overview of Project

In this project, we assisted a promising playright, Louise, who wants to Finance her play 'Fever'.  She approximates a budget of over $10,000.  This project uses excel to order, classify, and study crowdfunding data to determine if there are specific elements that make a project campaign successful.  This project provides Louise with information regarding specific elements that will help her set-up successful campaigns of the same category type.  

### Purpose

The purpose of this analysis is to determine how different campaigns fared in relation to their launch dates and fundraising goals. We provide Louise with not just data, but also written analysis and visualizations to help her understand how to incorporate components from other campaigns to provide the greatest level of success in her own.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

**For this analysis we used pivot tables and pivot charts to provide visualized campaign outcomes based on the campaign launch date.**

To perform the analysis of Outcomes based on Launch Date, we must first make all the data readable.  This involved changing the deadline and Launched-at columns from Unix timestamps to dates in a standard format.  

1. In a new column, add the heading "Date Created Conversion."
2. Enter the formula where X is the first data cell of the Launched_at column: "= (((x/60)/60)+DATE(1970,1,1)"

Then we created a new colum labeled "years" and using the "YEAR()" function pulled the year from the "Date Conversion Column".

From there we put subcategories into their own column.  This was done by using the "Convert Text to Columns Wizard". 

<img src="CreateSubcategory.PNG" height="200">

<img src="CreateSubcategory2.png" height="200" width="600">

<img src="CreateSubcategory3.png" height="200" width="600">
                                           
Next, we created a pivot table filtering by parent category and years.  The column value was equal to "outcome", rows values equal to "date created conversion", and values equal to "outcome". The column labels were filtered to show only "successful", "failed", and "canceled" outcomes. We set the parent category equal to filter to ensure that we looking only at theater projects.  All campaign outcomes were then sorted to   After setting up the pivot chart we created a pivot line chart, selecting the "Line with Markers" style.  The filters used were based off what we are trying to provide information for Louise on - outcomes and launch date.

### Analysis of Outcomes Based on Goals

**For this analysis we used the CountIFS() Function to determine outcomes based on goal amounts for plays specifically.**

To determine the percentage of each outcome type (successful, failed, and cancelled), we must first find the number of each outcome type.  To do this, we incorporated use of the "CountIfs()" function.  In the prior assignment separated the parent/subcategory column into parent and subcategory columns allowing us to find the various outcomes of plays specifically.  After finding the number of occurances per outcome, we totalled them to be able to then calculate the percentage per outcomes.  This analysis is important because it provides Louise with information that allows her to see what the likelihood of her success would be based on her goal.  This allows her identify that she may need to employ different strategies based on her goal amount or potentially change her goal amount.

Using the CountIFS() function allowed us to apply criteria to cells across multiple ranges and count the number of times all criterial are met.  This is a much faster process than having to apply the criteria against individual ranges and further manupulate those results to find the number of times ALL criterial are met.  The specific CountIFS() function used here is: 

"=COUNTIFS(Kickstarter!$F:$F, "successful", Kickstarter!$D:$D,"<1000",Kickstarter!$R:$R,"plays")
 - Kickstarter!$F:$F, "successful" refers to the successful outcome type in that specific range
 - Kickstarter!$D:$D,"<1000" refers to the goal amount in that specific range
 - Kickstarter!$R:$R,"plays" refers to the subcategory in that specific range


### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. The most successful Kickstarter campaigns were started in May.  However, most of the least successful campaigns started in December.

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
