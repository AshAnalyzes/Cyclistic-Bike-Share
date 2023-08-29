# Cyclistic-Bike-Share

This case study is the final module of the Google Data Analytics certificate. Throughout this case study, I will be analysing historical data for a hypothetical company called Cyclistic, a Chicago based bike sharing company. The case study scenario is as follows:

You are a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members.

You can check out the Tableau dashboard I created with this analysis [here](https://public.tableau.com/app/profile/ashleigh.eaves/viz/CyclisticRidershipNov2022-Apr2023/Dashboard1](https://public.tableau.com/app/profile/ashleigh.eaves/viz/CyclisticRidershipNov2022-Apr2023/Dashboard2)

# Data Preparation

I downloaded the last 6 months of data and opened a sample to investigate what has been collected. I note that there are 13 columns ride IDs, bike type, start and end times of rides, start and end station identifiers such as name and location, and member type of the rider. 

# Cleaning the data

I had hoped to use SQL functions to check for both duplicate values and errors within the text strings, however being so new to SQL coding, I was not able to figure out how to do this, so instead spot checked the excel spreadsheets for these things using excels in built functions such as “remove duplicates”. I found no instances for either, and continued with analysis. During these checks, I did find some instances of missing start and end station information. In some of these cases, it may have been possible to use data points that were available (such as end station longitude) to identify which stations these were and re add them back into the data set, but this again proved a bit too difficult for me and so I opted to simply remove them. 

Using the start and end timestamps, I created additional columns for the month of the ride, day of ride, and the length of the rides in seconds and minutes. From here, I wanted to check the data for any irregularities, so I checked the average length of the rides in minutes, as well as the minimum and maximum ride length. This showed that there were rides with negative values, and also rides which lasted for more than 1 day. I decide to filter out these irregularities, as well as any rides with a length of 0 minutes. With the new data, we have an average ride length of 12.5 minutes, a minimum ride length of 1 minute and a maximum of 1,437 minutes. 
To make the days of the week easier to analyse, I convert these into names rather then numbers, so 1 turns into Sunday and so on. 

I’m interested in understanding more about the types of routes taken, not just the start and end locations seprerately, so I also create a “route” column by concatenating start and end station names. 

# Analysis 

Members took far more rides than casual riders. Of the 1,183,505 rides taken in the 6 months dataset, 73% were completed by members. Although share of ridership decreased for casual riders throughout the winter months, it has been increasing since January, peaking at 34% in April. 

The average length of rides was 12 minutes. Casual riders tended to take longer rides than their membered counterparts, with casual rides 7 minutes longer on average than members. 

Members took more rides through the mid week, (Tuesday, Wednesday and Thursday) while casual riders were most active on Saturdays. When it came to the times of the rides, members appear to be using the bikes during the morning and afternoon peak hours, with 47% of all rides taken during morning and afternoon commuting times (7am – 9am and 4pm – 6pm). This effect seem less pronounced for casual riders who’s use of the bikes steadily increases throughout the day before decreasing sharply after 5pm. 

Casual riders appeared to have a stronger preference for the electric bikes compared to member riders, with almost half (49%) of casual rides occurring on electric bikes vs 40% for members. 

Taken holistically, this data suggests that members tend to use Cyclistic bikes as transportation to and from work, where casual riders appear to be using the bikes more for recreation. This theory is supported by the fact that casual riders often start and end their trips at the same location, where as members often take one way trips. Similarly, the routes members take typically occur in pairs, with similar numbers of rides per day in each direction. 

Finally, there appear to be differences between membership type in where the riders are going. The most popular routes for members seem to be around university locations, with routes near the Illinois Institute of Technology and The University of Chicago amongst the most ridden. Comparatively, casual riders tended to ride routes closer to the water and near recreational attractions such as Millennium Park, the Chicago Harbor and Oak Street Beach. While these recreational locations do not appear frequently in the member data, casual riders do also visit University locations. From this, I suspect there could be two categories of casual riders – recreational riders who use the bikes for fun, and students who have not converted into members. 

# Recommendations

Based on these findings, I would recommend the following courses of action to the marketing team:

1. Revisit the marketing strategy with a goal to convert the casual student riders to members. This could include a digital advertising campaign targeted towards students and with messaging tailored to them and promoting the cost saving benefits of becoming a Cyclistic member. The campaign should launch prior to the start of the collegiate year to generate awareness amongst student riders and encourage them to maximise use of their yearly membership for better cost per ride. 

2. To encourage membership take up amongst the recreational casual riders, Cyclistic could run digital OOH marketing in popular Harborside locations and with a higher presence among popular Cyclistic routes, promoting the electric bikes as a fun way to enjoy the city. The digital billboards should be run leading into the weekend during summer months and only during daylight hours, when most casual rides take place.  

# Final Thoughts

I really enjoyed undertaking both the Google Data Analytics Certificate and this capstone project. The project itself was a great way to challenge myself and further develop the skills I acquired throughout the course. It also highlighted some skills I still need more practice on, so I have put together a list of things I’d like to be able to do better for my next portfolio project: 

1. Increase skills at checking and cleaning the data prior using SQL to analysis. E.g identifying duplicates, editing missing data etc. 
2. Become better at working with and manipulating dates and timestamps in SQL. 
3. Work on arithmetic operators in SQL to better be able to calculate things like % of totals. 
4. Rely less on creating additional tables in SQL and learn functions for inserting columns or variables into existing tables. 
4. Improve data visualization skills in Tableau.
