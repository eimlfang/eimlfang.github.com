---
layout: post
title: "PushShell"
date: 2015-09-11 12:03:45 +0800
comments: true
categories: 
---
试图创建一个脚本__CreateNewBlog.sh__用来发布博客:  

```  
#! /bin/bash
printf "Please Input your new Blog Name->"
read BLOG_NAME
rake new_post["$BLOG_NAM"]
echo "Created $BLOG_NAME"
```  
```
$ cd octopress
$ /Users/besprout/Desktop/CreateNewBlog.sh

```
  
接着出现了  
  
```
Please Input your new Blog Name->pushsh
Hello pushsh
Enter a title for your post: PushShell
mkdir -p source/_posts
Creating new post: source/_posts/2015-09-11-pushshell.markdown
$ cd source/_posts/2015-09-11-pushshell.markdown  
```

但是还需要我输入博客名称,且继续学习脚本吧！

  