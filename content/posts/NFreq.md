---
author: 
title: NFreq package
date: "2017-10-06"
tags:
- post
---

## Homemade package to calculate neighborhood density and frequency

One of my current projects involves a whole bunch of wrangling with linguistic data--and it seems like I am doing the same thing over and over again. Therefore it might in fact be more prudent to slow down at the beginning, and build packages that can automate some of these processes and provide better replicability and flexibility for future work. 

My second R package is `NFreq` and it does a bunch of things. For a given set of words (or nonwords), it can calculate for each word:

 * its degree (number of neighbors based on the 1-edit distance),
 * return a list of its neighbors, and 
 * calculate neighborhood frequency (average frequency of its neighbors). 

Finally, one thing that I built into the package is the ability to specify your own reference corpus to calculate these values against.

As always I welcome all of your feedback and comments!   

Since `NFreq` is not hosted on CRAN, there are a few extra steps required to download it--I've attached documentation below that has specific instructions for downloading and using it (see the Vignette).  

* [Github repo](https://github.com/csqsiew/NFreq)
* [Vignette](https://github.com/csqsiew/NFreq/blob/master/vignettes/NFreq-vignette.pdf)
