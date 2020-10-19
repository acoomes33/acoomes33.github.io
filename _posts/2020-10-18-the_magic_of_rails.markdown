---
layout: post
title:      "The Magic of Rails"
date:       2020-10-19 01:16:09 +0000
permalink:  the_magic_of_rails
---


After using Sinatra, a lower-level Ruby framework, in the last project, I was excited to see what this "magical" framwork called Rails was all about. During the first week of learning Rails, I was blown away by the functionality that Rails brings compared to Sinatra, especially since I could basically create most of my Sinatra app with one line of code:

`rails g scaffold`

Of course, for this project I avoided using the scaffold generator, but I made sure to make full use of the resource generator which produced the right amount of automated code for each of the models. I was also impressed with the amount of helpers available to ruby programmers. Form helpers like form_with and the subsequent fields_for that takes care of nested forms help make versatile forms that can DRY up your views, while other helpes like link_to and button_to can create quick links to other pages that are understandable and uncomplicated. 

One thing I really wanted to take advantage of were the vast amount of ruby gems available for use. While a surplus of gems can complicate projects and can possibly lead to security issues and issues through discontinuation of gems, finding ones that fit a need and are reliable can become a great help in any application. A couple gems that really helped my project were the CanCanCan gem and the BetterErrors gem. The CanCanCan gem came in handy for the authorization components of my recipe application. After installing the gem onto the project, running this line in the terminal: 

`rails g cancan:ability`

creates an Ability model file that is setup to be used. Once it is created, you"ll see an initialize(user) method inside the class, and this is where you can put in your authorization requirements. Mine for example used this code excerpt to set up user authorization for only their specific recipes and comments: 

`can :read, :all
      can :manage, Recipe, user_id: user.id
      can :manage, Comment, user_id: user.id`
			
The first line allows all users to read all of the recipes and comments submitted by other users, while the last two lines basically only allow the user that a certain recipe and comment belongs to to modify it in any way.

the other gem, Better Errors, cleans up the standard error webpage that pops up when in the server and allows for more functionality to figure out the underlying issues. After installing the "better errors" gem and a corresponding "binding of caller" gem in the development group of gems, it replaces the old error page with an interactive page that allows you to interact with the code, almost like a byebug, while also showing the path the application went through until reaching the error. These two gems along with others helped immensely in the making of my app, and would highly recommend others take advantage of the vast ocean of gems out there in the Ruby-verse, although I would be remiss to not issue a warning of Gem Madness that can take ahold of an unsuspecting programmer like myself.
