# 1. Introduction

![22L3W0T2QG_2.jpg](attachment:22L3W0T2QG_2.jpg)

Rental bike also called bike sharing, has become common and popular transportation in urban areas due to its convenience and the rise in awareness for environmental sustainability. 

The public rental bike system allows the public to rent a bicycle from one docking station and return to another. In Seoul, Ttareungyi, Seoul's rental bike system, was started in 2015 and is available for anyone above the age of 15. Ttareungyi was a great success, and with the high use of the public, the available docking stations and bikes have gradually inclined. There are currently 800 bike renting stations in Seoul. 

This personal public transportation has furthered shown a soaring demand with Covid-19. With people trying to avoid congested and crowded transportations, the number of Ttareungyi users in 2020 rose by 24% from the previous year to reach 2.78 million.  (Bahk, 2021) 

# 2. Selection of project methodology

In an exploratory study done to understand the factors that influence the selection of data science process management methodology, Saltz and Holtz uses the the Technology-Organization Envrionment (TOE) framework. (Saltz, Holtz, 2021) The framework help them identify different factors to to consider from those that !!! influence the project from the people in it and the external factors for a data science project that involves software engineering. Hence, I have decided to use the same framework when choosing which methodology to choose, yet look at different criteria for them. 

TOE framework looks in to the technology factors which look into the data used, organization factors which look into the people, and the envrionmental factors which looks into factors such as who we work with and the the nature of service we plan to provide. 

Two to three critical criterias were identified for each factors.

**Technical factors:**
* Data collection and cleaning is expected to take shorter than most project as the app for the bicycles has been collecting most of the data needed.
* Data analysis needs to be done to understand the data. 
* Predictive models are needed to be created which indicates that iterations would be required.  

**Organization factors:** 
* There are only 4 people working in the project.
* Members have relatively no experience in data science project.
* Members have knowledge of the different methodology but doesn't show much prefernce in either.

**Envrionmental factors:** 
* Business requirenment is quite clear, however, there are still some vague part of the project that has not been decided.
* It is agreed to have the web-based app ready in 3 month. 


Then before looking into all the different methodologies, some of them can be eliminated by the two important factors. The two factors I belive to be essential is the experience of the members and the clarity of the business. Members with relative few experience would easily get lost when given too much felxibility and less guidance, such as Srcum Development, but also a methodology, like Waterfall, that limits them too much and has a tight schedule can make it hard to follow. 

Most methods starts with understanding the business context and implementing them depends on how much is known about the requirenment and whether it is prone to change. In this case while the data science part is quite fixed and clear, the software development would need a more agile method that can help address few uncertainity of the web-app. 

With those two factors in mind, I was able to come up with the four methodologies that can help the project be successful. Then these were further analyzed in a chart, this time all factors identified above were examined. ![framework_table.png](attachment:framework_table.png)


For this project TDSP methodology was chosen combined with Kaban. TDSP is described as an “agile, iterative data science methodology that helps improving team collaboration and learning”. (Ellis, 2008) It is a more detailed and up-to-date data science methodology that allows one to have a more detailed business understanding at the beginning of the project to align pur goals with our client through defining SMART (Specific, Measurable, Achievable, Relevant, Time-bound) objectives and identifying the data sources. Furthermore, it addresses one of the problem that are faced in CRISP-DM, lack of team definition "by defining four distinct roles (solution architect, project manager, data scientist, and project lead) and their responsibilities during each phase of the project lifecycle." (Martinez, Viles, Olaizola, 2021) 

TDSP is not without flaws. Cons about TDSP that are mentioned a lot are the steep learning curve, fixed sprint, and high dependance on Microsoft's services and policies. The former two is why I have decided to used Kanban together and would be discussed later on. The "high reliance it has in Microsoft does complicates the boarder use of it" (Martinez, Viles, Olaizola, 2021), yet it also makes documentations easier and the services produce reports that help us trace back history.

Kanban is a popular framework used to implement agile and DevOps software development. One of Kanban's most competitive advantage over other methodology is that it help teams become more efficeint by visualizing and improving workflow. In fact, according to 1st State Kanban Report, of 10000 companies 78% mentioned the main benefit gained from using Kaban is increased visibility of flow and the next highest one was improved delivery speed/throughput. Hence, when used together with TDSP it will help give more guidance for the members through graphics and help things be completed in time. Furthermore, with an agile method we would be able to continuously iterate and improve the approach. 

# 3.  Definition of business need

## Problem definition

One of the main responsibilities of Seoul City for its bike-sharing system is developing approaches to manage its rebalancing procedure. With the incline in bike-sharing users, the biggest problem that arises is that Seoul City isn't able to provide a stable supply of rental bikes. According to the “Barriers and facilitators to public bicycle scheme use: A qualitative approach” research, lack of accessibility/spontaneity was identified as a significant factor to the barrier to bike-sharing usage. (Fishman E) That is, the inefficiency can result in a decrease in customer satisfaction and lower the usage of bike-sharing. Yet, there are only a limited number of bikes that can be put out for rent due to the scarce docking spaces. Should Seoul City can understand the user’s behavior and predict the number of bikes that would be in use, they would be able to prepare more bikes for rent on the days they are expected to have higher demand. 

Seoul City has provided the data on the number of bikes rented and the details of the day from the season, wind speed to whether or not it is a holiday. Hence, the goal is to use this dataset to help Seoul City’s bike-sharing team to predict the number of bicycles that are expected to be in use and save the disappointment of the bike-sharing users by accommodating their demand. In addition, the data visualization would help the bike-sharing team to gain insights into their user’s behavior. 


## Target Audience

The target audience of the app would be the workers who work in the Seoul City'S public officers that are responsible for managing bike-sharing.

![Persona.png](attachment:Persona.png)

## Questions to be answered using dataset

* What are variables that are relevant to the changes in bike-sharing demand?
* What is the best way to predict the bike sharing demand? 
* If a machine learning model is used what model should be used?

# 4. Data preparation and exploration

The data we have is the Seoul Bike Data and it consists of 8760 rows and 14 columns (variables). 

The 14 original variables are: 
*	**Date**: The day of the day in the year  
*	**Rented Bike Count**: Number of rented bikes per hour
*	**Hour**: The hour of the day
*	**Temperature (°C)**: Temperature per hour
*	**Humidity (%)**: Humidity in the air in %
*	**Wind speed (m/s)**: Speed of the wind in m/s
*	**Visibility (10m)**: Visibility in m
*	**Dew point temperature (°C)**: Temperature at the beginning of the day
*	**Solar Radiation (MJ/m2)**: Sun contribution
*	**Rainfall (mm)**: Amount of rain in mm
*	**Snowfall (cm)**: Amount of snow in cm
*	**Seasons**: Season of the year (4 seasons)
*	**Holiday**: If it is a holiday period
*	**Functioning Day**: Whether it is a Functioning Day

With the Seoul Bike dataset loaded, the first work done was looking into the column names. The columns that were too long or included symbols were cleaned and made shorter. This would make it easier to call them later when more work would be done in looking into the dataset. Then the missing values were checked. This particular dataset had no missing values, so the data type of each column was looked into next. The Date columns were saved as an object hence it was changed to date type data. Then some more columns were created using the date columns, as we wanted to see and understand the data more deeply: Year, Month, Day, DayofWeek, and Year_Month columns (variables) were created. Lastly, a new column Night_Day was added, where 6, typically when people wake up to get ready to work, till 18, when people get off work, was considered daytime. This new column was added as I believe it would be able to show more insights into bike renting behavior with the time of the day. 

Each of the new columns (variables) represents: 
*	**Year**: The year of the data.
*	**Month**: The month of the data.
*	**Day**: The day of the data. 
*	**DayofWeek**: What day of the week the data is for. 
*	**Year_Month**: The year and month are concatenated, and the day of the date is eliminated. 
*   **Day_Night**: Whether it is day-time or night-time.

Then without changing the data further I decided to investigate how many data were from 2017 and how many were from 2018. There are 744 data for 2017 and 8016 for 2018. When plotted in a bar chart using Year_Month, it’s clear that for 2017 we have very little data because the data from 2017 are for December which 2018 lacks. A very similar bar graphed is plotted right below this time with Month Vs. Count, and it is the same as the one above just that the 2017 December data was put at the back. Through this bar graph, we can know that June and other hotter months have more bikes rented and colder months have relatively fewer bikes rented. 

<div>
<img src="attachment:Bar_month.png" width="700"/>
</div>


The box plots were graphed to see the outliers and to understand the number of bikes rented for different variables. The boxplots show that the number of bikes rented data, which is the Count variable, would be skewed to the right. From the boxplot plotted for seasons, we can infer that summer is the season with the most bike rented as the mean is the highest, which collaborates with the finding we had previously with the Month Vs. Count bar graph. Another important point here with the boxplots is that all data are from when the bike renting system was functioning, hence the Function Day variable isn’t going to provide any insights. 

<div>
<img src="attachment:boxplot.png" width="700"/>
</div>


Then a bar graph was made with the number of bikes rented to the hour of the day. There are two peaks in the number of bikes rented in the day. The two peaks occur at 8 when people usually go to work and 18 (6 pm) when work usually ends and the bike would be returned. 

<div>
<img src="attachment:count_vs_hour.png" width="700"/>
</div>


Then with a similar idea, two-point plots were created for the number of bikes rented for each hour, but how they differ for different variables. The first one shows how it is for days that are holiday and days that aren’t holidays, and the second one show for each day of the week. The interesting insight gained from these two graphs was that the graphs show a similar pattern for Weekdays and Not Holiday, and the Weekend data and the Holiday data have similar patterns. I was curious if this was because during the Holiday a greater number of bikes were rented on Sunday and Saturday, and vice versa. Yet looking at the pivotal table (can be seen in the code section) that doesn’t seem to be the case. Hence, it can assume that users of the bike renting system tend to use the bike renting system in similar behavior on holidays and on the weekends. 

<div>
<img src="attachment:bar_hour_feature.png" width="700"/>
</div>


Then the data with numerical variables such as Temperature and Visibility was looked at in their statistical description. A correlation map was created as well to just get an idea of how each of them correlated to each other and count. The Dew Temperature (DPtemp) and Temperature (Temp) variables have a very strong correlation of 0.91. 

<div>
<img src="attachment:corr_map.png" width="700"/>
</div>

Before saving the new modified data, final touches were made as more insights from the data were found through the data exploration. The Function Day (Func_Day) and Dew point Temperature (DP_Temp) were dropped. The Function Day as found out previously in the box plot was shown to have no impact on the number of bikes rented so it was eliminated. The Dew Point Temperature variable is the temperature of the morning with hyper correlation with the Temperature variable, so it doesn’t seem necessary to have. Hence, after all the final touches the data was saved as "df_prepared.csv".

# 6. Reference 

Bahk E., (2020). Seoul City's bike-sharing service becomes safer with soaring demand. [online] koreatimes. Available at: <https://www.koreatimes.co.kr/www/nation/2021/04/281_306366.html> [accessed 16 October 2021].

Canuma, P., (2021). Data Science Project Management in 2021 [The New Guide for ML Teams] - neptune.ai. [online] neptune.ai. Available at: <https://neptune.ai/blog/data-science-project-management-in-2021-the-new-guide-for-ml-teams> [Accessed 15 October 2021].

Data Science Process Alliance. n.d. Team Data Science Process (TDSP). [online] Available at: <https://www.datascience-pm.com/tdsp/> [accessed 17 October 2021].

Deeper Insights. n.d. How to run a Data Science Team: TDSP and CRISP Methodologies. [online] Available at: <https://deeperinsights.com/how-to-run-a-data-science-team/> [accessed 13 October 2021].

Fishman, E. Washington, S. and Haworth, N., (2012). Barriers and facilitators to public bicycle scheme use: A qualitative approach. Transportation research part F: Traffic Psychology and Behaviour, 15, 686–698. [accessed 11 Oct 2021].

Martinez, I. Viles, E. and G.Olaizola, I., (2021). Data Science Methodologies: Current Challenges and Future Approaches. Big Data Research, 24, p.100183. [accessed 23 Oct 2021].

Naydenov, P., (2021). Top Reasons Why Companies Use Kanban [Infographic]. [online] Kanbanize Blog. Available at: <https://kanbanize.com/blog/why-use-kanban-infographic/> [accessed 25 October 2021].

Saltz, J. and Hotz, N., (2021). Factors that Influence the Seletion of a Data Science Process Management Metholody: An Exploratory Study. Hawaii International Conference on System Science, 54, [accessed 7 Oct 2021].

Siderova S., (2018). The Top 10 Benefits of Kanban | Nave. [online] Nave Blog - Expert tips and guidelines for Kanban teams. Available at: <https://getnave.com/blog/kanban-benefits/> [accessed 20 October 2021].

