---
author: 
title: experiments in R
date: "2022-03-12"
tags:
- post
---

## Programming Psychology Experiments in R with `jaysire` (and how to host it on your own server)

I got really excited when I watched [this video](https://www.youtube.com/watch?v=BQMDOxWGrQg) where Danielle Navarro was describing the `jaysire` (j-psy-r) package she wrote for creating psychological experiments in R. This is a real gap in the space of "things that R can do really well", plus I really don't want to have to learn how to code in Javascript AND don't want to pay Gorilla.sc $ each time I download a participant's data AND just want to do anything and everything from the comforts of R. 

The [reference manual](https://jaysire.djnavarro.net/) and tutorials are really well-written, so despite the title this blog post isn't going to focus on how to use the package. Rather, the aim is to provide walkthrough the steps I took to get an experiment hosted on a cloud provider, and how to make sure that the data is saved. I needed to write this out because I will forget the steps if I don't. 

### Get your webserver up and running.

My cloud provider of choice is Linode (you can check them out [here](https://www.linode.com/?r=332b4d319fa740c19f7a3503bd2c033d1163d92c) and full disclaimer this is my personal referral token). Learnlinux.tv has a great set of Youtube videos that I followed to get it up and running. Here is what I did:

1. Get a linode running (I went with the cheapest $5 option and Ubuntu LTS 20.04). 
2. Set up SSH keys, add limited user, disable root log in, set up automatic updates (good basic server habits).
3. Connected my domain name to the server (this can take up to a day as it depends on when the records get updated). 
4. Enabled https with a SSL certificate from certbot (especially important if you are intending to run participants). 

It sounds like a lot but it is just the first 5 videos of this [playlist](https://www.youtube.com/playlist?list=PLTnRtjQN5ieb4XyvC9OUhp7nxzBENgCxJ). 

### Get the server ready for deployment of `jaysire` experiments 

#### 1. Install apache and php 

SSH into your server and run the following: 

```
sudo apt install apache2 php
```

Before you run the `run_webserver()` function to deploy your experiment that you have created using `jaysire`, you'll need to do two things. (I only found this out after quite a lot of time!)

#### 2. Give your limited user read/write access to the `/var/www/server_data` on your server.

The `run_webserver()` function requires that the limited user has the ability to write files into the `/var/www/html` folder. Change the `$USER` to your username. 

```
sudo chown $USER:www-data /var/www/html 
sudo chmod g+s /var/www/html
sudo chmod o-rwx /var/www/html
```

With credit to this [Stack Exchange answer](https://askubuntu.com/questions/749697/how-do-i-give-myself-access-to-var-www-to-create-and-edit-files-and-folders-in). I didn't need to edit the configuration files on Apache as the default was just fine. 

#### 3. Set up the `/var/www/server_data` folder on your server. 

You need a folder on the server where the webserver has permissions to write to. By default the experiment will write the data to this folder on your server `/var/www/server_data`. You'll need to set this up by typing the following commands into the terminal. 

```
sudo mkdir /var/www/server_data
sudo chgrp www-data /var/www/server_data
sudo chmod 775 /var/www/server_data
```

With credit to this (Github issue](https://github.com/djnavarro/jaysire/issues/8).

### Deployment! 

Run this in your R console:

```
run_webserver(
    path = '"path to your experiment on your local computer",
    experiment_folder = "experiment", # rename accordingly
    ssh = 'user@server.com, # where user = your username and server.com = your server's IP address (easily found on the Linode dashboard)
    keyfile = "~/.ssh/id_rsa",
    webserver_configured = TRUE
)
```

Note that this assumes that the ssh key that you've connected your server to in Step 1 is `id_rsa` (if you've followed the learnlinux.tv tutorial this would be correct). 

You can also download all the data files on your server with the following: `download_webserver(ssh = "user@server.com", keyfile = "~/.ssh/id_rsa", to = ".")`. It basically downloads all the data in the `/var/www/server_data` folder. 

You can check out a demo here: https://experiments.csqsiew.xyz/demo1/

### Multiple experiments 

You can certainly have a whole bunch of experiments running at the same time. I did this by creating subfolders in the `var/www/html` folder and moving the experiment files there. This offers good practice for learning how to use the command line. So `good_exp` folder in there would be accessible by `server.com/good_exp` , and so on. I also manually tweaked the `record_result.php` file in the `experiment/resource/script` folder so that the .csv file will carry the label of the experiment for easy sorting of the files later on. 

That's it! Hope that someone out there might find this useful. I found `jaysire` easy to use and am looking forward to deploying a bunch of my experiments written with this package very soon. 

