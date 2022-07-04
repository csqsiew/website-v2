---
author: 
title: enhance your productivity with the command line
date: "2022-03-25"
tags:
- post
---

## Command Line Utilities for Maximizing Productivity

Over the past year, I have been slowly but surely transitioning into a Linux set up for my research workflow and also for managing my personal tasks. What started out as a fun thing done over the weekends has blossomed into a productivity machine powered by the command line. My system is still a work in progress, for sure, but experimenting with a bunch of applications has led to more than a handful of sweet finds that have increased the speed and efficiency of a number of computer-based tasks. 

In this blog post, I'll share the ones that have optimized my workflow to a really high degree. Hopefully you'll find this list interesting and useful! 

### 1. File manager - *nnn, ranger* 

I have to work with a ton of files so having a really fast application for managing and organizing files is really central for an efficient workflow. Finder and most other GUI file browser applications are too slow. *nnn* is blazingly fast. A couple of keystrokes and I can copy and paste files, rename files, move files, make a new folder - all without having to drag my finger across a trackpad. It is also really easy to move between tabs and jump to a specific folder. *nnn* is also really customizable - I added shortcuts to folders that I need to access frequently and a sweet drag and drop plug in so that I can quickly grab the file I need to drop it into an email as an attachment. 

*ranger* deserves a special shoutout - while not as nimble as *nnn*, I like the ability to preview text files and PDFs, and a snappy way of yanking file names and file paths. 

*nnn*: https://github.com/jarun/nnn

*ranger*: https://github.com/ranger/ranger

### 2. Calendar - *calcurse*

I don't know if it is just me, but I have always found GUI calendars to be really clunky. So discovering *calcurse* was a game changer. No more clicking through weeks and months to get to a specific date - a single keystroke brings me to the next month and a couple more takes me to the specific date I want. My hands never need to leave the keyboard while I flip through my weekly agenda, insert new appointments, delete or update events. No more clicking on tiny drop down menus to get to the right hour.

An important must-have feature of a calendar is the ability to sync to other devices. *calcurse* can be configured with CalDAV to sync to a remote calendar on your server (also works with Google calendar - but do yourself a favor and get off Google...). I got mine synced to my calendar on Nextcloud. I do have to run the `calcurse-caldav` command to initiate a sync each time I start the app on a different computer, which may be a bit of hassle if you are used to automatic sync, but in fact, I appreciate the "explicit-ness" of having to call for a sync. It sort of feels like commiting a change in git.  

*calcurse*: https://calcurse.org/

> 2022/07/04 update: I am running in weird bugs with calcurse that I am not able to solve. Sadly, it means I have to reture this terminal app. My calendar replacement for now is the calendar within the [Vivaldi](https://vivaldi.com/features/calendar/). It is more keyboard based than most other calendar GUIs, and Vivaldi itself is not a bad browser.      
 
### 3. Search - *ag, fzf*

Super fast search is an essential tool in any knowledge worker's arsenal. Information is only really useful if you are able to retrieve it quickly amongst all the other stuffz you gotz. *fzf* helps me look for any file via searching for terms in the title and/or the file extension. Its github has a bunch of useful bash functions that uses *fzf* to do a lot of useful things, and you can just copy the ones that you need into your `.bashrc` file. In particular I found `fd()` and `fh()` really handy for quickly changing directories and searching through my command history. Simple but super effective. I have *fzf* set up so that I get a preview of the file in the terminal, and can easily open the file in *vim* or some other program depending on the file type.  

Over the course of my day-to-day work, I not only have to search for PDFs and documents, but also for information embedded inside the file. For instance, I may want to find a specific code chunk in a R script for wrangling a specific kind of dataset or producing a similar visualization from a previous project. This is where I turn to *ag*, the silver searcher. I throw a bunch of search terms at it and can usually recover the information that I need, even though I may have well forgotten the name of the file, or where the file was stored. When combined with a bit of regex knowledge, you'll be unstopable. 

*ag*: https://github.com/ggreer/the_silver_searcher

*fzf*: https://github.com/junegunn/fzf (github), https://github.com/junegunn/fzf/wiki/examples (examples) 

### 4. Text editing - *Emacs, Vim* 

Like many people, I got caught up in the Zettelkasten craze. This led to me to spend a lot of time searching for the best note taking/writing app, and reading everything on the internet about which app was best. I went with Trilium and Obsidian for a bit, but in the end I figured that simple plain text files with a powerful text editor is the way to go. (See this [blog post](https://sive.rs/plaintext) by Derek Sivers where he provides a list of reasons for why he writes only in plain text--I agree with them all). 

I have been using *Emacs* for several months now, and just started learning *Vim*. *Emacs* and org-mode are best for complex documents related to project management or GTD systems. *Vim* is great for a quick fast note that needs to be taken. While I am by no means an expert in *Emacs* or *Vim*, spending some time learning the keybinding will give you immense superpowers with text that you could have not imagined previously. 

Org-mode in *Emacs* is a beast. I use it to organize my GTD system, take notes on absolutely everything, and organize my research projects. My projects begin life as a simple text file with the .org extension mode that gets built up with a detailed log of ideas, challenges, solutions, analysis notes, experimental design, relevant references, conceptual arguments and framing, a log of data collection progress. When I get to the writing stage, I reorganize all of this information into a manuscript and export it to an ODT file with an APA6 template. I could go on and on about org-mode... 

*Vim* is the new kid on the block - but I am really liking it. I am writing this blog post in *Vim*, and have started using the *Vim* shortcuts in RStudio. The modal approach to text editing is fascinating and I am looking forward to learning more about it. 

*Emacs*: https://www.gnu.org/software/emacs/

*Vim*: https://www.vim.org/

### Summary 

As you can tell, the strategy is actually quite straightforward--use as few GUI apps as possible and use the keyboard wherever possible. On most work days I typically only have the terminal, browser, PDF reader, RStudio, and Emacs open (with Zoom or Skype for video conferencing when necessary). A nice plus is that I have the exact set up on both Linux and MacOS (thanks to Homebrew!). With these CLI apps, I can craft the system that allows me to move around much more efficiently in a computing environment.  
