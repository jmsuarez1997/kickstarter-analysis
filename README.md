# Kickstarter-Analysis with Excel
An analysis on Kickstarter data to uncover trends

## Overview of Project

### Purpose
Louise is planning to launch her play, *Fever*, and wanted more information on the outcomes of campaigns in comparison to funding goals and launch dates. The analysis took a deeper look into crowdfunding data to find whether campaigns were successful, failed, or canceled (aka outcomes) in relation to launching dates. The analysis also shows the campaign outcomes based on the initial funding target goals.
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
The first analysis performed is shown in the graph titled *Theater Outcomes Based on Launch Date*. The analysis shows us the quantity of either successful, failed, or canceled outcomes of campaigns in the theater category based on the months they were launched. The results allow identification of which times of the year are the best to launch a successful theater campaign.

![Theater Outcomes Based on Launch Date](https://raw.githubusercontent.com/jmsuarez1997/kickstarter-analysis/main/Resourses/Theater_Outcomes_vs_Launch.png)

To find this, a pivot table was created using the *Kickstarter_Challenge.xlsx* data set. Then a line graph was generated with the number of outcomes on the y-axis and launch date by month on the x-axis. The data was then filtered to only show only data from the parent category, theater.

### Analysis of Outcomes Based on Goals
The second analysis performed is shown in a chart titled *Outcomes_vs_Goals*. The analysis shows the percentage of successful, failed, canceled campaign outcomes in the subcategory plays in relation to the monetary goal amount requested. The result allows identification in ranges of $5000 starting with less than $1000 and ending at $50,000 what percentage of campaign outcomes were successful, failed, and canceled. 

![Outcomes_vs_Goals](https://raw.githubusercontent.com/jmsuarez1997/kickstarter-analysis/main/Resourses/Outcomes_vs_Goals.png)

To find this, use the `=COUNTIFS()` function to filter down specific data from the Kickstarter_challenge.xlsx data set. Make columns for Goals, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled. In the Goals column create 12 ranges/rows of $5,000 increments starting with <$1000 and ending with >$50,000. Then use the `=COUNTIFS()` to find the Number Successful, Number Failed, and Number Canceled. Filter to show only the subcategory plays, respective goal ranges, and respective outcomes. In the Total Projects, find the sum of the values from the Number Successful, Number Failed, and Number Canceled using the `=SUM()` function. Next, find the percentages for Percentage Successful, Percentage Failed, and Percentage Canceled using the formula `= (Value / Total Value)*100`. Finally, create a line chart with percentages on the y-axis and ranges of goals on the x-axis. 

### Challenges and Difficulties Encountered

An obstacle that may be encountered in the second analysis is using the correct syntax to filter properly for the goal ranges. When filtering the first value will be <1000. For the following ranges, use the = sign to include that value in your range. The second range should look like the following:

`=COUNTIFS('Kickstarter Data'!$F:$F,"successful",'Kickstarter Data'!$D:$D,">=1000",'Kickstarter Data'!$D:$D,"<5000",'Kickstarter Data'!$R:$R,"plays")`

Note how the beginning of the range uses the >= sign to include that value in the count and the ending value of the range uses < and is 1 dollar amount over the desired range so the function stops counting at the exact amount desired.

## Results

What are two conclusions you can draw about the Outcomes based on Launch Date?

The most successful time to launch a campaign is in the month of May. The least successful time to launch a campaign is in the month of December. The highest number of failed campaigns stays consistent from May to August at around 40-50 failed theater campaigns per month. 

What can you conclude about the Outcomes based on Goals?

Most successful campaigns for plays had goals set for under $5000. As the goal amount increases, the percentage of successful campaigns declines, and the percentage of failed campaigns increases. So the lower, your campaign goal is the higher chance you will have a successful campaign. Campaign success increases to 67% between the funding range of $35,000 and $45,000, but this is most likely due to the lack of data for this range. 

What are some limitations of this dataset?

We narrowed the data down to just plays and theater categories on the Outcomes_vs_Goals & Theater Outcomes Based on Launch Date graphs, but there are only 1,047 and 1,369 data points respectively. This is a relatively low number. For example, in the second analysis when the successful campaigns increased to 67 % for the funding ranges of $35,000 and $45,000 there were only 9 entries total for those data ranges. That's not enough data to make a fair analysis.

The amount of money requested for a project or goal for the campaign is not the only factor that should consider for having a successful and failed campaign. Other factors should be considered like what type of team or cast is on the project, how good the script is, etc., but we don't have this information in our data set. 

What are some other possible tables and/or graphs that we could create?

A Pledged vs Goal scatter plot graph with a best fit line could be created to see how likely campaigns received 100% of their requested funds or exceeded their goal. You could also graph the data over years instead of months and see if donors are pledging more funds this year vs previous years. 
