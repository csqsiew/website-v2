---
author: 
title: data art using pi digits
date: "2018-03-14"
tags:
- post
---

## Data Art in R: A case study using a bunch of pi digits

Happy Pi Day everyone! 

Many people have done data art with pi digits (see this awesome [collection](https://www.r-graph-gallery.com/portfolio/data-art/) of data art in R)--but I wanted to see if I could reproduce it myself by hacking some code together and am fairly pleased with the results. I think a couple of these images might become my new desktop wallpaper :)  

Concept: Plot a "random walk" of sorts where the angle (amount of rotation) of the step which the random walker takes depends on the digit in the sequence. 

|1| Download a million digits of pi from this [website](http://pi2e.ch/blog/2017/03/10/pi-digits-download/). Get it into a dataframe with one digit in each row.   

|2| Create a dataframe that indicates the x- and y-locations for each digit. This step is a bit tricky... Basically draw a circle and split it up into equal parts and figure out the x- and y-distances for the center point of the circle to get there... The legend below should help. 

![](/img/legend.png)

|3| Merge the dataframes from steps 1 and 2. 

|4| Plot the individual line segments via a for loop. Voilà!   


**First 11 digits of pi**

<img src="/img/10pi.jpg" alt="Drawing" style="width: 500px;"/>   


**First 101 digits of pi**

<img src="/img/100pi.jpg" alt="Drawing" style="width: 500px;"/>   


**First 1001 digits of pi**

<img src="/img/1000pi.jpg" alt="Drawing" style="width: 500px;"/>   


**First 10001 digits of pi**

<img src="/img/10000pi.jpg" alt="Drawing" style="width: 500px;"/>  


**First 100001 digits of pi**

<img src="/img/100000pi.jpg" alt="Drawing" style="width: 500px;"/>  


You can find the R script (`make_a_pi.R`) to create these figures [here](https://github.com/csqsiew/website/tree/master/content/Rcode). 
