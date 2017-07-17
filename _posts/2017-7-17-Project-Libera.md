---
layout: post
title: Project Libera
---
  
![Libera Logo](../../images/logo.png "Project: Libera Logo")  
  
  
Project: Libera is an intelligent user-content connector that I designed for my passion project during my 3 months at Metis' [Data Science Bootcamp](https://www.thisismetis.com) in Chicago. Powered by a custom designed webcrawler and the magic of machine learning, Project: Libera is a tool for automatically seeking out new web content related to Data Science.  
  
### Why Libera?  
As an aspiring data scientist I'm constantly trying to find new articles/blog posts/information to give me a leg up on the competition, but the pay off between time spent looking for articles and actual quality articles read is sporadic. Some days you hit gold. Some days you spend 4 hours looking at videos of [munchkin cats doing cute things](https://www.youtube.com/watch?v=nEFX-EQYTxE) forgetting why you're on the internet in the first place.  
  
Libera was designed to eliminate the risk of distraction and also to expand my blog collection out of my own social network and list of sites that I already view. Because isn't that the real beauty of machine learning? Making a computer do something for you, faster than you, and potentially even better than you. But you can't train a machine without data. So I went to my old data science haunts and collected a good amount of blog posts and then let a blind web crawler hit all of their direct links. These were then hand labelled with a simple flask app I made for quick data editing and before I knew it I had a web cralwer that used a Naive Bayes classification model to determine if a blog was related to data science.  
  
### Taking it Further  
  
While having a web crawler that could get me new content started to address the time suck that is web browsing, I quickly realized it wasn't nearly enough. What if I'm on a data viz kick? Or maybe I'm trying to buckle down on big data. Perhaps I just need some statastiscs. Just having a collection of blogs about data science didn't work if I was looking for something more specific. To address this, I took my blog text corpus and used Natural Language Processing, dimensionality reduction, and unsupervised learning techniques to automatically identify subtopics. With automated collection and subtopicing I set out to make a front end Flask based web app to tie it all together.  
  
## A Look at the Front End
 
With a large collection of posts and segmentation into subtopics complete, I turned to make Libera more user friendly. Searching out web pages in a MongoDB isn't exactly the best UX for my purposes. So I turned to Flask and made a landing page, user sign up form, and recommendation feed. When a user signs up for recommendations, they are given an interest form to select what exactly it is they're looking for:  
  
![Interst Form](../../images/interests.png "Project: Libera Interest Form")    
  
Once they're selected their interests they're brought to a feed of recommendations. These recommendations are presented using Embedly cards to give snapshots of the content and the icons on the left allow for user interaction.

![Feed](../../images/card.png "Project: Libera Recommendation")  
  
The user's account is linked to a SQL database that I hope to one day use for collaborative filtering. The web crawler also takes in a list of all inbound links for each post for use in a page rank style system. The more I work on Libera, the more new directions for growth arise. It is certainly something I am proud of and something I plan to continue developing. For now, it lives alone on my computer, but I'm toying with the idea of launching it. I'll be sure to post here if I do!  

## Keeping it Flexible 

Libera was clearly designed with my interests and my use in mind. But I also wanted to make somethitn that was flexible enough to be repurposed for others' needs. I hosted my code on [github](https://www.github.com/paulfblack) and included the flask app I used for hand classification. To reinitialize on a new topic you just need to find some blogs related to a certain topic and keep collecting and labelling data until you can train a classificaiton model on it.  
  
When training the model I prioritized precision on posts classified as related. This protects the user from seeing really unrelated recommendations, but can come at the loss of some good content. As far as the machine learning techniques, they can be used as is, but it is always best to compare different methods and not to assume that what works for one data set will work for another. I am still working on getting some details worked out on the back end, but I hope one day to return to the beginning and see if I can't get this up and running for all of my interests, maybe even munchkin cats.

## What I Learned  
  
This process was incredibly educational. It involved SQL and NoSQL databases, multiple machine learning algorithms working together, was hosted on the cloud, and required a good amount of front end development. But what I really learned while designing Libera was how to take an idea and see it through to conclusion. When I started Libera, there was no data. No clear outline about what I wanted and no framework or structure for how to get there. As I moved forward in this process ideas grew and died and I had to be flexible and persistent to deal with roadblocks that I hit along the way.   
  
The resources available for learning new approaches and understanding how to address new problems are so incredible and vast. With enough creativity and grit, there really isn't much that can't be done. Data is everywhere and just because someone hasn't put it into a free/accessible data set for your use doesn't mean you can't create it for yourself. I would advise every aspiring data scientist to dream big and buckle up; lofty, unrealisitic, and even unreachable goals make for the best education.  
 
