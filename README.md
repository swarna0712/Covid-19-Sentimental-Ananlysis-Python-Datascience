# Covid-19-Sentimental-Ananlysis-Python-Datascience

COVID-19 TWEETS SENTIMENT ANALYSIS
Abstract:
This paper explores and discusses how people globally reacted to the corona virus pandemic.
We used social media, specifically twitter, to do so as social media is a means of expression
around the world. Hence, we can gauge the sentiment levels per day by using data from it.
We use the tweepy library in order to extract data from tweet ids and find the mean sentiment
per day by taking the mean sentiment of all tweets for a particular day. This mean sentiment
is plotted graphically against the date along with covid data such as the number of covid
deaths and the number of covid cases to find any relationship between the tweet sentiment
data and the covid data. From this data analysis, we test the hypothesis that the mean
sentiment of people was always greater than the number of new covid cases. The number of
covid cases can be taken as a measure of negativity as covid is the reason for the downfall in
mental health of people around the world. We therefore prove that the mean sentiment of
tweets per day was positive and the mean sentiment score per day increased as the negative
sentiment increased (number of covid cases). We can therefore infer that the social media
tried to spread positivity during this tough time.

Introduction:
With the current covid-19 pandemic that has taken over the planet, we wanted to see how
people around the world were affected mentally during the peak of lockdown. We decided to
take to social media as the means to do so, specifically twitter. Our project is about checking
how the number covid cases and deaths have affected the mean sentiment of tweets from
20-03-2020 to 9-10-2020 and therefore check if there is any relationship between the covid
numbers and the mean sentiment of tweets. 
Dataset:
Our data sources are: tweets data and covid statistics data set.
tweets data: 
https://ieee-dataport.org/open-access/coronavirus-covid-19-tweets-dataset#files These
consisted of the tweet id and sentiment of each tweet posted each day having active hashtags
and keywords related to covid-19.
From the 206 files we had (each corresponding to a day in 20-03-2020 to 9-10-2020)
Columns included: tweet id, tweet sentiment score
Active keywords and hashtags : &quot;corona&quot;, &quot;#corona&quot;, &quot;coronavirus&quot;, &quot;#coronavirus&quot;, &quot;covid&quot;, &quot;#covid&quot;,
&quot;covid19&quot;, &quot;#covid19&quot;, &quot;covid-19&quot;, &quot;#covid-19&quot;, &quot;sarscov2&quot;, &quot;#sarscov2&quot;, &quot;sars cov2&quot;, &quot;sars cov 2&quot;, &quot;covid_19&quot;,
&quot;#covid_19&quot;, &quot;#ncov&quot;, &quot;ncov&quot;, &quot;#ncov2019&quot;, &quot;ncov2019&quot;, &quot;2019-ncov&quot;, &quot;#2019-ncov&quot;, &quot;pandemic&quot;, &quot;#pandemic&quot;
&quot;#2019ncov&quot;, &quot;2019ncov&quot;, &quot;quarantine&quot;, &quot;#quarantine&quot;, &quot;flatten the curve&quot;, &quot;flattening the curve&quot;, &quot;#flatteningthecurve&quot;,
&quot;#flattenthecurve&quot;, &quot;hand sanitizer&quot;, &quot;#handsanitizer&quot;, &quot;#lockdown&quot;, &quot;lockdown&quot;, &quot;social distancing&quot;, &quot;#socialdistancing&quot;,
&quot;work from home&quot;, &quot;#workfromhome&quot;, &quot;working from home&quot;, &quot;#workingfromhome&quot;, &quot;ppe&quot;, &quot;n95&quot;, &quot;#ppe&quot;, &quot;#n95&quot;,
&quot;#covidiots&quot;, &quot;covidiots&quot;, &quot;herd immunity&quot;, &quot;#herdimmunity&quot;, &quot;pneumonia&quot;, &quot;#pneumonia&quot;, &quot;chinese virus&quot;,
&quot;#chinesevirus&quot;, &quot;wuhan virus&quot;, &quot;#wuhanvirus&quot;, &quot;kung flu&quot;, &quot;#kungflu&quot;, &quot;wearamask&quot;, &quot;#wearamask&quot;, &quot;wear a mask&quot;,
&quot;vaccine&quot;, &quot;vaccines&quot;, &quot;#vaccine&quot;, &quot;#vaccines&quot;, &quot;corona vaccine&quot;, &quot;corona vaccines&quot;, &quot;#coronavaccine&quot;, &quot;#coronavaccines&quot;,
&quot;face shield&quot;, &quot;#faceshield&quot;, &quot;face shields&quot;, &quot;#faceshields&quot;, &quot;health worker&quot;, &quot;#healthworker&quot;, &quot;health workers&quot;,
&quot;#healthworkers&quot;, &quot;#stayhomestaysafe&quot;, &quot;#coronaupdate&quot;, &quot;#frontlineheroes&quot;, &quot;#coronawarriors&quot;, &quot;#homeschool&quot;,
&quot;#homeschooling&quot;, &quot;#hometasking&quot;, &quot;#masks4all&quot;, &quot;#wfh&quot;, &quot;wash ur hands&quot;, &quot;wash your hands&quot;, &quot;#washurhands&quot;,
&quot;#washyourhands&quot;, &quot;#stayathome&quot;, &quot;#stayhome&quot;, &quot;#selfisolating&quot;, &quot;self isolating&quot;

covid statistics data: We considered the WHO dataset for covid-19 which contained the
number of cases, cumulative number of cases, number of deaths and cumulative number of
deaths for each day in our chosen time period.
Columns included: Date_reported, Country_code, Country, WHO_region, New_cases,
New_deaths, Cumulative_cases, New_deaths, Cumulative_deaths
Pre-processing and Data cleaning:
tweets data: 
Each sample file contained sentiment score of a tweet and its tweet-id. 1000 samples from
each file were taken where any non-existing tweet-id row was ignored(removed). Using the
tweepy library, we extracted the date of posting, number of retweets and number of likes of a
tweet were extracted using tweet-id. This data was used to calculate: mean sentiment, mean
retweeted sentiment, mean liked sentiment, most agreed with sentiment, where:
Mean sentiment =
Mean retweeted sentiment = mean of sentiments of top 20% highest retweets tweets
Mean liked sentiment = mean of sentiments of top 20% highest likes tweets
Most agreed with sentiment = mean (Men retweeted sentiment, mean liked sentiment)
Mean retweeted sentiment, mean liked sentiment and most agreed with sentiment were
calculated to check if the mean of posted sentiment varied drastically with the sentiment
score of the most popular tweets (showing what sentiment people agreed with the most)
Covid-19 statistics data: We considered the WHO data-set containing the number of cases,
cumulative number of cases, number of deaths and cumulative number of deaths for each day
in our chosen time period.
Colums dropped: Country_code, Country, WHO_region,
The rows were grouped together based on date and sum of each column of New_cases,
New_deaths, Cumulative_cases, New_deaths, Cumulative_deaths for each day.

Final Cleaned data set:
Both cleaned data sets were merged based on date. Any NaN value in a column was imputed
by mean value of that column. Date values also had to be unified to the ‘dd-mm-yyyy’
format.
Missing Data percentage: 9.2233%
Columns of the final data set-
Date
Mean Sentiment – mean sentiment of that day
Mean retweeted sentiment – mean sentiment of top 20% retweeted tweets
Mean liked sentiment - mean sentiment of top 20% liked tweets
Most agreed with sentiment – mean of mean retweeted and mean liked sentiment
Number of tweets – number of tweets having active keywords posted that day

New cases- new covid-19 cases confirmed cases of that day
Cumulative cases - total number of covid-19 cases confirmed so far
New deaths - new covid-19 cases confirmed deaths of that day
Cumulative deaths - total number of covid-19 death confirmed so far
All the above columns were normalised before further testing, to fit in the range of 0 to 1.
If the mean sentiment (of the day) &lt;0.5 , this implies that the sentiment that day was
negative.
If the mean sentiment (of the day) &gt;0.5 , this implies that the sentiment that day was positive.
If the mean sentiment (of the day) =0.5 , this implies that the sentiment that day was neutral.
Since the data is normalised, it would make sense when we compared it with other columns
as they all fall within the same range.

Exploratory Data analysis:

On plotting the line graphs of normalized covid related variables and tweet related variables,
the graphs of mean sentiment and new deaths seemed to have a correlation and peaks and
drops seemed to be present on the same date. Here the date on the x-axis is represented as
numbers where 0 is 20-03-202 and 206 is 9-10-2020. (this was done for more readability).

This same trend/relationship was seen with mean retweeted sentiment and mean liked
sentiment with the number of new deaths per day. The graphs also proved that the sentiment
of the most popular tweets (wrt retweets and likes) did not vary from the mean sentiment of
the day as much as we thought it would.

We also found that as number of covid cases
increased, the number of tweets related to covid
also increased. This was expected as the more
number of covid-19 cases, the greater it is
discussed as the more awareness and information
is spread about it.
We also wanted to see the same trends in the
peak of the spread of the virus (and the peak of
lockdowns globally), so line graphs were plotted
for the months of June, July and August (these months were selected as all countries had
large number of covid cases at this time and were in their peak number of cases. No country
had successfully fought off the virus yet). The trends of the means sentiment of tweets and
the number of covid deaths were found to be very similar.

Hypothesis Testing:
All the above analysis lead us to the hypothesis that: However much the number of new covid
deaths increased, the mean sentiment of tweets always was more, i.e. however negative the
global atmosphere became people spread positivety (to a greater extent) instead of spreading
their current negative emotions. Here we are considering that the number of deaths due to
covid leads to a negative atmosphere/sentiment as it gives reason for it. Therefore, we tested
2 hypotheses:

 People’s positivity is always greater than the number of covid cases (sentiment was
more positive with the increase in negativity)
 People’s sentiment was not equal to the number of covid cases, i.e., they were not
positive in the same magnitude as the negativity.
NULL HYPOTHESIS (H O ) – The difference between means of the mean sentiment and
mean number of cases is lesser than or equal to 0
ALTERNATIVE HYPOTHESIS (H 1 ) – The difference between means of the mean
sentiment and mean number of cases is always positive
SIGNIFICANCE LEVEL (ALPHA) – The significance level is 0.05
H0 : μx - μy &lt;= 0
H1 : μx - μy &gt; 0
alpha value is : 0.05
actual_z: 1.6448536269514729
hypo_z: 4.816478261987024
Reject NULL Hypothesis
Results and discussions:
From the above hypothesis tests, we can determine that: taking number of covid cases as a
measure (and reason) of global negativity, the mean sentiments of tweets were always
positive to a greater extent than the global negativity (number of covid cases). This can help
us say that social media tries to create a positive impact on world even during the toughest of
times.
We can also infer that during the months of
June, July and August, a correlation between
the mean sentiment of tweets and the
number covid deaths exists. This can be seen
by the heatmap of those months.

As social media is seen as an outlet for
emotions (especially twitter), we had
expected to see a decline in sentiment score
with increase in covid cases and deaths, we
found out the opposite. This also maybe due
to the fact that most corona related tags are positive related tags such as: #stayhomestaysafe
and this may have led to the increase in positive sentiments as people tried spreading more
positivity as number of cases increased at an alarming rate.
