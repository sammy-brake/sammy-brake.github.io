---
layout: post
title:      "Rails with Javascript Project"
date:       2019-07-06 15:37:51 +0000
permalink:  rails_with_javascript_project
---


For this project, I incorporated a Javascript front end with my already existing Rails app. Working on this project showed me how much I've learned as a developer both with code and with debugging. 

This project was different from my past projects in that I wasn't building an application from the ground up. I wanted to tread lightly and make sure each new feature worked and also didn't break anything else in my app. 

The first thing I did was attach my event listeners and through in 'debugger' so I could see that they were working. Initially, I completed the project checklist with everything except using Javascript Model Objects. I used serializer to return my Active Record models in JSON and appended them to the dom. I got everything to work that way (SO I THOUGHT....but more on that later) and then I wrote code for a constructor function and incorporated that into my code. 

Initially, I think I was mentally resisting converting my JSON data into JS models because I wasn't fully understanding the benefit. It just seemed easier to return the JSON and append the data directly to the dom. Once I did make my JS objects, I really did see the benefit. I made a method on the prototype that would format the html that I would want appended to the DOM and the functionality was really so much improved compared to just appending the JSON directly to the DOM. I also created a method that would convert the format of the date.  I am glad that I did it both ways, because I was really about to see the difference and learn more about what my code was returning. 

Finally, after I finished everything, I realized that something I had added broke one of my forms. I dug into my code and saw that my form for booking was suddenly routing to a different controller. Weird. I tried manually specifying the route for my "form_for" but it didn't fix it. I looked at my JS and realized I had written code that was hijacking ALL my forms, not just the specific form I wanted to manipulate. That was a simply fix! I just used my inspector tools in the browser to figure out the default id that Rails was giving the form I wanted to select and I changed my code from 'form' to 'form.new_field_experience' and everything was working again! 


