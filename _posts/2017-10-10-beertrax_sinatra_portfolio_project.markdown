---
layout: post
title:      "BeerTrax: Sinatra Portfolio Project"
date:       2017-10-10 17:20:02 +0000
permalink:  beertrax_sinatra_portfolio_project
---


I finished my Sinatra portfolio project today, or at least what I would consider to be version 1.0.  It is an application to track beers that you've tried, and it allows you to provide a rating, comments and some basic information about the beer.

I used the ruby gem "corneal" to generate the scaffolding of the app itself, which was a huge time saver and made Sinatra feel much more similar to Rails in that way.  I was very glad to have found that gem!

The greatest lesson I learned in creating this app is that planning is paramount.  There were very important decisions to be made about models and relationships between models that would have huge implications on the functionality of the app.  From the beginning I was certain that I needed a user model and a beer model, but what about breweries, ratings, comments?  How should the models be related to one another?

I spent some time playing around in Tux, a ruby gem that allows you access to all your code in the console, to get a feel for the appropriate models and relationships, and to make sure I had the database set up properly.  This proved invaluable as it allowed me the ability to troubleshoot the structure of my app before even beginning to code.  I made a couple changes to my models and my migrations through this process and really saved some time by not jumping right into the code.

In the end, I decided to keep the app fairly simple, while maintaining the ability to build it out further in the future if I want to.  I created models for users, beers and breweries.  Users have many beers, as well as many breweries, through beers.  Beers belong to a user and a brewery.  And breweries have many beers.

While these models and relationships work fine, they do present some limitations in functionality.  If two users list that they've had the same beer in the app, that beer is created in the database twice, since a beer belongs to a specific user.  The two beers don't know anything about each other.  This is fine for the purpose for which I am intending this app to be used for now, which is for a user to be able to track and take notes on beers that they've tried.  However, it would need to be modified in order to allow for greater functionality, such as the ability to see all comments or ratings about a specific beer.

I used some basic Bootstrap to make the app look nice, applying styles to the form elements and incorporating a navbar, and I incorporated some logic in the views so that the appropriate buttons are displayed depending on whether or not the user is logged in, is the user who created the beer they're viewing, etc.  I also used flash messages to provide feedback to the user if they don't fill out the forms properly, try signing up with a username that has already been taken, logging in with an incorrect password, etc.

