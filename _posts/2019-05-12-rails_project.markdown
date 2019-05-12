---
layout: post
title:      "Rails Project"
date:       2019-05-12 17:54:59 +0000
permalink:  rails_project
---


Edventurous

Edventurous is an app that allows users to browse field trip and guest speaker opportunities and schedule them. There are three models associated with this app: users, field experiences, and bookings. Bookings represents a joins table that allows users to have many field experiences and field experiences to have many users. 

In the future, I would like to build out the capacity for some users to be administrators who can approve the field trips or guest speakers that other users would like to book. Also, I would eventually like to build out the ability for users to use a nested form to create a new field experience while they are making a booking, if they do not want to choose from the existing field experience options. 

For now, I have an app that allows a user to create an account either by filling out a Sign Up for or by signing up with Facebook.  Once they are signed in, they can browse Field Experiences or search for a Field Experience that pertains to a certain subject, like biology or art. If they would like, they can schedule a Field Experience for a particular date. 

This app was pretty clear cut, the major issue I ran into was with my User sign in process. My session sign in form was taking me to the users sign UP form and that really threw me for a while. I noticed that the url of the errors page was /users, which was my big clue that I wasn't being routed where I needed. A Flatiron instructor gave me the awesome advice of using my browsers inspector tools to see where my "Submit" button was directed and - sure enough - Rails was overiding my routes to go to the @user controller. I manually specified where I wanted my form to post to and the problem was solved!  As a self paced student, I find myself not interacting with the general Flatiron community very often, but this was an experience that made me so grateful for being a Flatiron student. 
