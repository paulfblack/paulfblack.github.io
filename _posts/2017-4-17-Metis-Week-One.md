---
layout: post
title: Blank Canvassing 
---
## **Week One at Metis DS Bootcamp**
----
This week at Metis we looked at [MTA data](http://web.mta.info/developers/turnstile.html) and moved from green to clean, or, rather, cleaner. For a group of novices with disparate backgrounds this was no simple task and certainly not one we imagined we would finish in five days. But we did! We survived and managed to pull of actual presentations, with actual graphs of actual data! But more importantly, we learned. A lot. And, for the rest of this post, I will share a small portion of this weeks take aways! This is meant partly to be a refresher for my future self and partly to be a helpful resource for the imaginary people that I imagine will read this.   

----  
  
## The Premise:  
  
Your team has been contracted out by Women Tech Women Yes (WTWY) International to provide optimal canvasser placement recommendations for an upcoming gala in New York City.  To this end you will use the publicly available [MTA data](http://web.mta.info/developers/turnstile.html) and any other data you deem relevant. The goal is not simply to have street teams placed where there is the most foot traffic, but rather to place them in way such that they can gather the most signatures from individuals who are likely to attend the gala and contribute to WTWY's goal.  
  
----  
  
## Tools:  
  
### 1. Natural Curls, and cURLS, Naturally.
> For this project we explored two main ways of getting the data into a usable form: curl and panda's read_csv to read directly from a live url.  The former involves downloading the file directly to your computer by typing `curl {web address} > filename.txt` into the command line. The `>` tells curl to write the information in the web address to the file 'filename.txt'. Leaving this out will simply cause said information to print to the command line.  Alternatively the `-o` flag can be used in place of `>`. If a file already exists at 'filename.txt' this file will be overwritten by default.  To append instead of overwrite `>` can be replaced with `>>`. Having the data stored locally allows for pandas to read the csv data more quickly than if it is being pulled directly from a website.  Once the data is stored it can be brought into a dataframe using `pd.read_csv('file_directory_and_name')`. The alternative approach is to use `pd.read_csv()` to read directly from a webpage. This takes longer, but can be useful if internal memory is an issue.  To do this just replace 'file_directory_and_name' with the website url. **Note:** Both of these approaches work because this file is already in CSV format; my advise to people trying to get their feet wet with data: use CSV files they're (relatively) easy to work with.  
  
  
### 2. Reading is Fundamental.
> The eighth wonder of the world is most certainly the existence of programming libraries.  There's nothing more beautiful than thinking, "man I wish I could do -x-" and realizing not only has someone built a way that you can, they are willing to let you have access to it. For free. In this week we were exposed to a fair amount of programming libraries and their documentations (e.g [pandas](http://pandas.pydata.org/pandas-docs/stable/10min.html), [datetime](https://docs.python.org/2/library/datetime.html),[numpy](https://docs.scipy.org/doc/), [pickle](https://docs.python.org/3/library/pickle.html)). Learning to explore and understand library documentations is, well, fundamental. I mean, you could always built everything you do from the ground up (if you're an expert programmer with all the time in the world), but chances are someone (realistically a group of someones) has already made something to accomplish a similar task that can be used for your purposes.  Chances are they also did it better.  
  
### 3. [Panda Panda Panda](https://www.youtube.com/watch?v=4NJlUribp3c)  
> This is the real gem we got from this week and every data enthusiasts must have tool. Combine it with [NumPy](https://docs.scipy.org/doc/) and you're running math equations over hundreds of thousands of cells of data in seconds. Combine it with [MatPlotLib](http://matplotlib.org/2.0.0/index.html) and you're plotting lines, histograms, and scatter plots of data you've only begun to understand. And even by itself you can count the number of unique types of degrees in you faculty list dataframe `faclist['degrees'].nunique()`, checking how many grades you have recorded for how many students `grades_list.shape`, or figuring out how many weather records you have for each day of the week `weather_record['day_of_week'].value_counts()`. 

----  
  
## It's all data to the Greek.  
It may not seem like it from this brief overview of the tools used this week, but the tools mentioned in this post are actually incredibly powerful.  **cURL** is how you find and pull your data, finding public CSVs is easier than you'd think! **Libraries** are all about asking the right questions, mostly, can I do x? If so, how? Free programming education is out there if you know where to look, have the curiosity to look for it, and the grit to teach yourself, ask for help, teach yourself again, fail, and not stop trying until you succeed. **Pandas** is quite aplty named. It's cute. It's not that scary on face value and a lot of it is intuitive. It's not math heavy. But in spite of all this, it's incredibly powerful and worth checking out the documentation and tutorials on! With these three tools, the premise posed at the beginning of this post can be addressed. Trust me, I did just that.
----
