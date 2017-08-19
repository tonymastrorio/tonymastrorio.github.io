---
layout: post
title:  "A Ruby Gem for the Baseball Hall of Fame"
date:   2017-08-19 16:54:43 +0000
---


After about a day of preparation spent watching videos and reading through code examples, and a full day of coding, I've built my very first ruby gem.  The gem scrapes data from baseball-reference.com on all of the players in the Baseball Hall of Fame.  On loading the app, it lists all the players, the year they were inducted, along with their total number of votes and vote percentage.  The app then allows users to select any player, by line number, to view some of their career statistics.

Although it's a fairly simple app, there is a lot involved in making it work.  First, there is the process of setting up your environment and making sure you have the correct folder structure.  The `bundle gem` command makes this process much simpler, although, as I discovered later, it doesn't always get things exactly right.  Then, there is the architecture, the process of planning out what your app will do and how it will work.  What classes will you have and how will they interact?  That's the tricky part.

For this project, I created three main classes.  The CLI class, which is loaded automatically by a line in my bin file, is responsible for displaying data to the user, getting the user's input and calling on the other classes.  The Scraper class actually scrapes the data from the baseball-reference.com website and then calls on the Player class to create the Player objects and give them all their attributes.

One of the hurdles I faced midway through the project was in testing my app, I found that it broke down in certain cases.  I built the app based on batting statistics, but those are not very meaningful for pitchers.  So, I had to add some logic to the app to display different attributes for pitchers.  Finally, some members of the Hall of Fame are managers, so I had to handle those fringe cases as well.

After building the app, there was the process of figuring out how to get the structure set up properly in order to publish it as a ruby gem.  The main challenge I faced here was that the gemspec file, by default, points to the "exe" directory to look for an executable file.  My exectuable is in the bin directory, so this wasn't working properly.  After a wild goose chase on Google and Stack Overflow, I finally found a bread crumb that led me in the right direction and got everything working properly.

One of the main reasons I've chosen this path as a web developer is because these skills allow you to build anyting you can think of.  This project is a great step in that direction, and the feeling of accomplishment after completing such a project is truly great.
