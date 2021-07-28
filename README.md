# just-go-dev-blog

This is the readme of my blog.

To install : 

- The framework is Jekyll. If you need a step-by-step guide on how to install Jekyll, 
please follow that [one](https://computingforgeeks.com/how-to-install-jekyll-on-ubuntu-18-04/) 
- You will also need to install Apache 2 or any webserver of your choice. To make the whole 
architecture simpler, I've put all the posts on an Apache 2 server. 


How does it work? :

The posts are compiled within the jekyll folder. The old posts are then deleted from the www folder of the webserver.
The newly compiled posts but also the old ones, from the jekyll severs are copied to the www folder. 
Once copied, they will appear on the blog.
The only server that matters are the files (posts,else) that are in the Jekyll folder


To write a post (an article):

- create a file with the following format `YYYY-MM-DD-title.markdown`.
- That file once compiled, will be turn into a HTML format 
- Inside of the markdown, please put the meta-info below

```
---
layout: post
title:  "`My title"
date:   YYYY-MM-DD HH:MM:SS +0000
categories: articles
---
``` 

To run it:

I've created an alias 

BU='rm -rf /home/myusername/www/_site && jekyll build --source '\''/home/myusername/cloned_projects/www/'\'' && sudo rm -rf /var/www/* && sudo cp -rf _site/* /var/www'

Once everything is ready for posting, I type `BU` and hit ENTER
