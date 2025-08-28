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

```yaml
---
layout: post
title:  "My title"
date:   YYYY-MM-DD HH:MM:SS +0000
categories: articles
---
``` 

To run it:

create an alias with a concatenated command. 

```bash
alias BU='set -e; \
  cd /home/andykw/blog.just-go.dev && \
    JEKYLL_ENV=production bundle exec jekyll build --source /home/andykw/blog.just-go.dev --destination /home/andykw/blog.just-go.dev/_site && \
      sudo mkdir -p /var/www/html/blog.just-go.dev && \
        sudo rsync -a --delete /home/andykw/blog.just-go.dev/_site/ /var/www/html/blog.just-go.dev/'
```

Once everything is ready for posting, type `BU` and hit ENTER

Note: 

To add up a few things

- Markdown basic syntax guide : https://www.markdownguide.org/basic-syntax/
- Troubleshooting : if you have issue with public-suffix -> https://talk.jekyllrb.com/t/could-not-find-public-suffix-3-0-1-in-any-of-the-sources-bundler-gemnotfound/1603
