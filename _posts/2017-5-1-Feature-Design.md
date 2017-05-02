---
layout: post
title: Feature Design 
---
## **This Week at that Data Science Crash Course**
----
Hello World! Back for a bit to post about my brief experience with feature design in my linear regression modelling challenge at Metis, Chicago.  

----  
  
## The Challenge:  
  
These past two weeks we've been working on linear regression modelling and data scraping (using Selenium and Beautiful Soup). Data scraping, 
for me, was the start of a very unhealthy love-hate relationship where for what felt like forever I gave my all and got very little in return. But that 
is an epic love story for another day, today I want to highlite the *feature design* that came after a beautiful conclusion to that suspenseful romance novel.  
  
For my linear regression model I attempted to use purely weather related data from wunderground.com to predict ground level ozone pollution (recorded by the EPA). 
It is important to note that ground level (or tropospheric) ozone forms when ozone precursors (often industrial waste) react with UV radiation (the sun) 
and form O3 (a pollutant that causes lung damage and shortens lives). Also important: wunderground.com's historical weather data pages (which I scraped) 
do not include UV index (which would increase prediction accuracy). The sensible option would have been to go get a csv file with UV indexes associated with dates, 
but the staid and stalwart experimenter in me wanted to see if I could do it with only the resources I had already collected!  
  
I couldn't. Or, rather I didn't, but I learned a bit along the way, which is a victory in my book. 

----  

## The (attempt at a) Solution:  
  
Wunderground.com's history weather data *does* have an hourly report of the weather conditions for each day. These conditions are qualitative descriptions 
like "clear", "sunny", or "overcast" and they are reported every hour and at every point of change in condition. This proved both an opportunity and a challenge. 
My plan was to take these hourly conditions and apply a numeric value for just how sunny that day was. Sounded easy enough, sunny would equal 1, 
scattered clouds: 0.75, partly cloudy 0.5, mostly cloudy 0.25, and anything else (overcast, rainy) would be a zero.  
  
The first problem I encountered with this was that not every condition lasted an hour. Mind you, I was looking at L.A. weather data so I probably could've 
made due by just saying 100% sunny all the time, but I wanted the most accurate quantitative depiction I could design. So, using some dateutil timestamps, 
I figured out how long each condition lasted and converted that to a percentage of an hour and then multiplied that by the number assigned to the condition. Then, 
I totaled up the values over the entire day and decided to test my progress. In theory, the higher the number, the sunnier the day, the more UV radiation, and the more tropospheric ozone pollution.  
  
I ran this through an OLS model to find that with an *incredibly* high likelihood, this parameter helped predict my target! (In the opposite direction than I had predicted). 
Furthermore, I had also included a parameter that was total length of day which meant I had introduced some autocorrelation; longer clear days would have a higher value 
than shorter clear days in both length of day and day condition.  
  
This last part was easy enough to handle: just divide the number by the length of the day, but that wouldn't fix my inverse relationship. Higher condition values, 
somehow meant lower ozone pollution levels even though they were sunnier days. Surely, my design could not have been so far off the mark, so what detail could I possibly be 
missing? Honestly, I'm still not entirely sure, but I have a hunch: wind.  
  
Now, my model took in some wind data to use as a parameter (max gust speed to be exact), but I had no way of tracking how windy a day was overall. What 
I did find was that higher winds increased pollution (presumably by plowing pollutants in from surounding industrial areas). My current hypothesis
is that overcast days often come with high ammounts of wind which my model completely missed! The effect of wind could outweigh the effects of direct sunlight 
such that sunnier days actually seemed to lower ozone pollution even though (all other things being equal) longer days clearly increased pollution. 
Really what I learned was that my design did not work and it was time to pull in UV index reports, but it got me better aquainted with my data and opened up new doors for inquiry.  
  
The real takeaway: try everything and never be afraid to fail. In many cases (this one included) "failing" at what you set out to do is actually *succeeding* in learning about the bigger picture, 
growing in your understanding of the true nature of the processes you're exploring and, if nothing else, you get to walk away knowing you tried.  
  
----  
