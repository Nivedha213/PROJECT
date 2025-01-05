Twitter Analytics-Dashboard

DASHBOARD LINK: https://app.powerbi.com/links/Q0TRbq5_H9?ctid=50ecd50c-6687-4469-b51f-b48715fca477&pbi_source=linkShare

Problem Statement

This dashboard helps to Track and visualize the  Twitter metrics such as tweets, retweets, likes, replies and followers over time. It helps to Analyse the sentiment analysis and emotion detection to understand public opinions and their emotions towards the brand to make it effective. It identifies the top influencers, media files, hashtags and keywords that relates to our brand and the industry. It helps in the Content and Timing metrics to know the top performing tweets and hashtags and to know the best time to tweet and their tweet frequency. By creating this dashboard, we aim to improve our social media strategy to engage with our audience more effectively and make data driven decision and analytical analysis to enhance our brand reputation and online presence.


Steps followed

Step 1 : Load data into Power BI Desktop, dataset is a csv file.

Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.

Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".

Step 4 : It was observed that in none of the columns errors & empty values were present in following all columns.

Step 5 : For calculating time, null values were not taken into account as only less than 1% values are null in this column, separate date and time was extracted from the time column.

Step 6 : In the report view, under the view tab, theme was selected.

Step 7 : Since the data contains Proportion of Total clicks ,only Total clicks is derived from DAX Function-(Sum Function) and dragged into Card Visual.

Step 8 : Visual filters (Slicers) were added for Four fields named "Month", "Date", "Tweet category", "IST hour", "Even engagement".

Step 9 : Card visuals were added to the canvas, representing Media views, Impression, Engagement Rate, Tweet Count, Sum of clicks, Tweet with more than 500 impression. Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into Total calculation.

        Although, by default, while calculating Total, blank values are ignored.
Step 10 : A Line chart was also added to the report design area representing the Trend over particular period of time .Other Line chart for impression over week ,Cluster Bar chart to show Tweet with sum of URL Clicks and other visuals.

Step 11 : Pie Chart Visual was used to represent Sections mentioned below,

(i) Hashtag Clicks (ii) URL Clicks (iii) User Profile Click In our dataset, Some parameters were assigned value 0, representing those parameters are not applicable for some Data.

All these values have been ignored while calculating Totals for each of the parameters mentioned above.

Step 12 : In the report view, under the insert tab, three text boxes were added to the canvas, Task mentioned were written for each page.

Step 13 : In the report view, under the insert tab, using slicer option i use a different styles of slicers to the report to get the desired design for the task.

Step 14 : Calculated measure was created to get the proportion of total clicks in which,

the following DAX expression was written;

TOTAL CLICKS = SUM('SocialMedia (2)'[url clicks])+SUM('SocialMedia (2)'[user profile clicks])+SUM('SocialMedia (2)'[hashtag clicks])

 A card visual was used to represent the Proportion of total clicks.

 ![1](https://github.com/user-attachments/assets/ac1c74cb-198d-44cc-8b0a-b108fd08f04d)


Step 15 : New column was created to find Even Date posted Tweet 

the following DAX expression was written;

EVEN DATE = IF(MOD(DAY('SocialMedia (3)'[Date]),2)=0,1,0)

Step 16 :  New column was created to find Odd Date posted Tweet
 
the following DAX expression was written;

Odd Date = IF(MOD(DAY('SocialMedia (4)'[Date]),2)=1,1,0)

Step 17 : New column was created to find the Tweet category 

the following DAX expression was written;

 TWEET CATEGORY = IF(CONTAINSSTRING('SocialMedia (3)'[Tweet],"HTTP"),"TWEET WITH LINKS",IF(CONTAINSSTRING('SocialMedia (3)'[Tweet],"#"),"TWEETS WITH HASHTAGS",IF(CONTAINSSTRING('SocialMedia (3)'[Tweet],".PNG"),"TWEETS WITH MEDIA","OTHERS"))).

Step 18 : New measure was created to calculate Tweet character count with below 20 .

Following DAX expression was written ,

Tweet CharCount 20 = if(LEN('SocialMedia (4)'[Tweet])>75,LEFT('SocialMedia (4)'[Tweet],FIND(" ",'SocialMedia (4)'[Tweet] & " ",20)-1),'SocialMedia (4)'[Tweet])

Step 19 : The report was then published to Power BI Service

![2](https://github.com/user-attachments/assets/32a5a607-b5c3-4d42-abe6-17b5539c7613)


Snapshot of Dashboard (POWER BI SERVICE)

![2](https://github.com/user-attachments/assets/32a5a607-b5c3-4d42-abe6-17b5539c7613)


Report Snapshot (POWER BI DESKTOP)

![3](https://github.com/user-attachments/assets/44ea4dd0-3f76-46ed-90d0-67199c231385)



Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following Task were worked out ,

1.Build a pie chart that represents the proportion of total clicks (URL clicks, user profile clicks, and hashtag clicks) for tweets with more than 500 impressions. Include a drill-down to view the specific types of clicks for each tweet.

SnapShot of Task 1

![4](https://github.com/user-attachments/assets/aca0aa84-c3d6-4331-b08d-f670e9bd9c9d)



2.Create a clustered bar chart that breaks down the sum of URL clicks, user profile clicks, and hashtag clicks by tweet category (e.g., tweets with media, tweets with links, tweets with hashtags). Only include tweets that have at least one of these interaction types and this graph should work only between 3PM IST to 5 PM IST apart from that time we should not show this graph in dashboard itself and the tweet date should be even number as well as tweet word count be above 40.

SnapShot of Task 2

![5](https://github.com/user-attachments/assets/6f406d8a-3f64-4856-b52e-4ef0be1c5f2e)



3.Create a line chart showing the trend of the average engagement rate over each month of the year. Separate the lines for tweets with media content and those without and this graph should work only between 3PM IST to 5 PM IST and 7 AM to 11AM apart from that time we should not show this graph in dashboard itself and the tweet engagement should be even number and tweet date should be odd number as well as tweet character count should be below 20 and need to remove tweet word which has letter 'C.

SnapShot of Task 3

![6](https://github.com/user-attachments/assets/847b9b2a-32da-4372-b860-9686239c0d02)















