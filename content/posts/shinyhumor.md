---
author: 
title: humorous phrases with shiny
date: "2017-10-05"
tags:
- post
---

## A shiny R app that randomly generates pairs of words

My first `shiny` R app! The humorous phrases shiny app generates a pair of randomly selected words from the 4,997 words from the recent Engelthaler and Hills [BRM paper on humor norms](https://link.springer.com/article/10.3758/s13428-017-0930-6). The user can click on buttons to indicate whether they found the phrase humorous or humorless, and a new word pair will be generated. 

Another really cool thing is that the app is set up to collect the responses provided by visitors. This will permit us to determine if there are certain phrases with characteristics that make them appear more humorous than other phrases. No other information is collected so the data is inherently anonymized. 

This was a very interesting project that, once again, broadened my ideas on what R can accomplish and represents a useful addition to my R toolkit. The app itself was easy to set up--thanks to this [excellent tutorial on shiny](http://shiny.rstudio.com/tutorial/) and once I got the concept of reactive objects with interactive inputs and outputs. The most challenging part was getting the output saved to an external file, as the documentation out there was a bit lacking and quite messy. There are multiple ways to get it done, but in my view the simplest and most straightforward method was to write the data to a temporary file and upload it to a Dropbox account using the `rdrop2` package. 

All the relevant scripts (minus my authentication token, of course!) can be found in the github repo below, in case it might be useful to others. If you have any comments or feedback, do get in touch! 

The app is hosted on shinyapps.io -- [check it out](https://csqsiew.netlify.com/studies/humor/) and contribute to science! 

* [humorous phrases](https://csqsiew.netlify.com/studies/humor/)
* [Github repo](https://github.com/csqsiew/shinyhumor)
* [Humor norms paper](https://link.springer.com/article/10.3758/s13428-017-0930-6)
