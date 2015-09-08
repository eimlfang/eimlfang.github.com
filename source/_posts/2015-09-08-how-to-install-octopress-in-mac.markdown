---
layout: post
title: "How to install Octopress in Mac"
date: 2015-09-08 15:58:54 +0800
comments: true
categories: 
---

# First Step: Install environment
## -Needs Tools
  Git,Ruby
## -Install Ruby
  Checking ruby versions of your mac,it is only supporting Ruby version upper than 1.9.3.
## -Install Octopress
  input:  
  **git clone git://github.com/imathis/octopress.git octopress**  
  git will clone Octopress from github to local dictionary named "octopress"  
  than input :  
  **cd octopress**
  
###   Install related tools
  **sudo gem install bundler**  
  **bundle install**  
  **rake install**  
  if you see warning: *"You have already activated rake 0.9.6, but your Gemfile requires rake 0.9.2.2."*  
  it means version of rake is 0.9.2.2,it is too old,need update rake,using command  
  **boundle update rake**.  
  Make sure all the previous steps are success and then you can go to next step.  
    
# Deploy blog
  I will deploy my blog to Github.  
  First, you need create a [responsitories](https://github.com/eimlfang/eimlfang.github.com) called eimlfang.github.com.  
  Than using **rake setup_github_pages**,input your url and password.  
  **rake generate**  
  **rake deploy**
  These two commands generate blog files and copy to *_deploy/* dir,than commit source to git.  
  **git add .**  
  **git commit -m 'Initial source commit'**  
  **git push origin source**
  Delopy done
# Write/Publish blog  
  create new blog:  
  **rake new_post["title"]**  
  **rake generate**  
  **git add .**  
  **git commit -am "Some comment here."**  
  **git push origin source**  
  **rake deploy**
  
  