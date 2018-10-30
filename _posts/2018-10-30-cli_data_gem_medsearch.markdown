---
layout: post
title:      "CLI Data Gem MedSearch"
date:       2018-10-30 20:39:36 +0000
permalink:  cli_data_gem_medsearch
---





For my CLI Data Gem, I needed to:
1. Provide a CLI
2. Scrape data from an external website
3. Allow a user to make a choice and then give information based on that choice. 
4. Avoid over-scraping a website
5. Use good OO Ruby code

The idea for my CLI Data Gem essentially fell into my lap.  I mentioned to a friend that I was working on scraping data from the web while I was working on Student Scraper and he said he wished he could do that for the spreadsheet he was making about different medications for a grant project.  BOOM - the idea for MedSearch was born.     

For me, the hardest part of this project was the initial set up and file dependencies.  I used [this](hthttps://bundler.io/v1.12/guides/creating_gem.htmltp://) tutorial for how to get started using bundler.  The tutorial has really clear cut instructions.  Looking back, I think my biggest hang up was forgetting to save my changes before running the program again. This was the first project that I completed using the desktop Learn IDE instead of the one in browser.  In browser, the changes automatically save when you move your mouse to the terminal but the desktop version doesn't do that.  I think I would make a change, forget to save, and then get an error based on my old code **but not realize it**. (embarrasing but true).  I created a gem using "bundle gem [name of gem]" twice before getting all my files set up and ready for my project code.   

Next, I added a "med_search" file to the bin to run the program from.  I also added three files to lib/med_search: MedSearch::Scraper, MedSearch::Drug, and MedSearch::CLI.  In lib/med_search.rb, I put all of the file and gem dependencies (open-uri, nokogiri, colorize) and made sure that all of other files required this overarching file.  

Each of my classes are created to organize specific tasks.  My MedSearch::Scraper class is tasked with scraping information from the website Goodrx.com.  MedSearch::Drug creates and stores drug objects for each medication searched by the user.  The MedSearch::Drug class helps me limit the number of scrapes done on Goodrx.com.  It also lets me communicate past searches to the user.  The MedSearch::CLI class is where I store the logic used to interact with the user.  

After my files were all set up, I made a basic CLI interface so that I could see what my code was building.  I wrote logic that would give the user a greeting and then ask if they wanted to look up a medication or quit.  I wasn't quite sure how to store the input and then use it in my scraping method, so I had to play with that a little.  

From there, I focused on my getting my scraper class to scrape the information I wanted from the drug.  The website I am scraping from happens to be very uniform, so that part was just a matter of opening up the site with the developer tools and finding the css classes.  After this, I went ahead and made my MedSearch::Drug class initialize method so that it could take a hash of attributes and create a new drug instance. 

I knew that I wanted to limit the amount of times the website would be scraped, so I created a method in the MedSearch::Drug class that would check to see if the drug class already existed before scraping the website for the information.  

At this point, I went back to my MedSearch::CLI to update the logic there based on the newer methods I'd created.  

The last issue I needed to tackle for my CLI Data Gem was figuring out how to handle it if a user gave input that my classes couldn't understand.  Until this point, any input that wasn't "list," "quit," or a medication on goodrx.com would just throw an error.  I used this [Bastards Book of Ruby link](http://ruby.bastardsbook.com/chapters/exception-handling/) to figure out error handling.  This was the first totally new type of code that I used for this project and I did a lot of googling to figure it out, but this guide ended up having a simple solution.  

Here is a screenshot of my CLI Data Gem at work.  

![](https://scontent.fmkc1-1.fna.fbcdn.net/v/t1.0-9/45195637_10105333540583881_4440712192236453888_n.jpg?_nc_cat=108&_nc_ht=scontent.fmkc1-1.fna&oh=dcf9ca3d12fb923976db9892f46090d4&oe=5C79299Dhttp://) 



