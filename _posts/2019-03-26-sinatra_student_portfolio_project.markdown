---
layout: post
title:      "Sinatra Student Portfolio Project"
date:       2019-03-26 14:55:11 -0400
permalink:  sinatra_student_portfolio_project
---



For this project, I build a full MVS Sinatra application. I've recently started using a time management app, Toggl, to track my time. According to my Toggl records, I spent about 7 hours researching and building this app.  Here is a breakdown of how I built my app:

1. I created a new repository in github using an MIT license. 

2. In my IDE, I used the "git clone" command followed by the link to my repository. 

3. I created my file structure. This part was easy. I already knew that I needed two models - a user and a review. I also had a pretty good idea of what views I would need. 

4. Using rake and ActiveRecord, I created my migrations. ActiveRecord makes it possible to map my models to my database tables pretty easily. The only tricky part with this is making sure that my column types and names correspond to what informatin I want to store for my models. I had to do this part a couple of times to get it right.  
5. I wrote my models, making sure to specify my "has_many" and "belongs_to" relationships between my models. 
6. I built my routes and views simultaneously. I used the "shotgun" gem frequently to make sure that each new capability could work before adding another aspect. 

Eventually, I built an app that has users that can sign up, log in, and perform CRUD interactions with reviews. 

One gem that I really got to know in this lab was bcrypt. Before this app, I wasn't entirely clear how to implement bcrypt to authenticate my users, but just this morning I utilized this blog post to help:
[bcrypt]http://bradschraglearns.com/bcrypt_and_the_magic_of_has_secure_password)



