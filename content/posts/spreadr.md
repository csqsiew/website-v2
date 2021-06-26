---
author: 
title: spreading activation in a network
date: "2018-06-01"
tags:
- post
---

## spreadr: A R package to simulate spreading activation in a network

The notion of spreading activation is a prevalent metaphor in the cognitive sciences; however, the tools to implement spreading activation in a computational simulation are not as readily available. Recently I published a paper in Behavior Research Methods that introduces the `spreadr` R package and shows how one can use it to implement spreading activation within a specified network structure to address research questions in different areas of cognitive science. The algorithmic method implemented in `spreadr` follows the approach described in Vitevitch, Ercal, and Adagarla (2011), who viewed activation as a fixed cognitive resource that could “spread” among connected nodes in a network.       

This is a paper that I am very proud of. I started writing the basic functions for `spreadr` way back in 2014 (after reading the 2011 paper), and have been working on it on and off for the past 4 years. During the first year of my post doc at Warwick I started re-writing the code into a more "user-friendly" format so that it would help me do my research more efficiently. I did a bunch of simulations with the package and figured that others might be able to use it for their own research, and perhaps I should write a paper.      

The reviews made the paper and the package even stronger, and `spreadr` benefitted from the input of people who were way more computationally savvy than me. I had help from Dirk Wulff who optimized the function with a healthy dose of C++. The package still a work in progress, but the aim of putting out this paper is to encourage cognitive scientists to explicitly consider how the structure of cognitive systems affects the way people process information. A simple tool like `spreadr` might help make this idea more concrete and help shift the balance away from research that overwhelmingly focusses on the cognitive process itself to research that considers the interaction between structure and process.     

Certainly the icing on the cake was `spreadr` getting accepted into the world of CRAN. I have come a long way from when I first started programming in R back in 2012 and couldn't even get a dataset to load in RStudio... The plan is to keep working on it and the latest version can always be downloaded directly from my github.    

If you have any comments or feedback, do get in touch. I hope you will find it useful.    

* [spreadr on CRAN!](https://cran.r-project.org/web/packages/spreadr/index.html)
* [Github repo](https://github.com/csqsiew/spreadr)
* [Vitevitch et al. paper](https://www.frontiersin.org/articles/10.3389/fpsyg.2011.00369/full)

