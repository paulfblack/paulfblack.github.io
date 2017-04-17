---
layout: post
title: Blank Canvassing 
---
Week One at Metis DS Bootcamp
----
This week at Metis we looked at [MTA data](http://web.mta.info/developers/turnstile.html) and moved from green to clean, or, rather, cleaner. For a group of novices with disparate backgrounds this was no simple task and certainly not one we imagined we would finish in five days. But we did! We survived and managed to pull of actual presentations, with actual graphs of actual data! But more importantly, we learned. A lot. And, for the rest of this post, I will share a small portion of this weeks take aways!  

----  
  
## The Premise:  
  
Your team has been contracted out by Women Tech Women Yes (WTWY) International to provide optimal canvasser placement recommendations for an upcoming gala in New York City.  To this end you will use the publicly available [MTA data](http://web.mta.info/developers/turnstile.html) and any other data you deem relevant. The goal is not simply to have street teams placed where there is the most foot traffic, but rather to place them in way such that they can gather the most signatures from individuals who are likely to attend the gala and contribute to WTWY's goal.  
  
----  
  
## Approach:  
  
###1. First Steps
> 1.1 Acquiring the Data
>> For this project we explored two main ways of getting the data into a usable form: curl and panda's read_csv to read directly from a live url.  The former involves downloading the file directly to your computer by typing `curl {web address} > filename.txt` into the command line. The `>` tells curl to write the information in the web address to the file 'filename.txt'. Leaving this out will simply cause said information to print to the command line.  Alternatively the `-o` flag can be used in place of `>`. If a file already exists at 'filename.txt' this file will be overwritten by default.  To append instead of overwrite `>` can be replaced with `>>`. Having the data stored locally allows for pandas to read the csv data more quickly than if it is being pulled directly from a website.  Once the data is stored it can be brought into a dataframe using `pd.read_csv('file_directory_and_name')`. The alternative approach is to use `pd.read_csv()` to read directly from a webpage. This takes longer, but can be useful if internal memory is an issue.  To do this just replace 'file_directory_and_name' with the website url.  
  
----  
  
## Results:  
  
----
  
## Lessons learned:  
  
---- 

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
