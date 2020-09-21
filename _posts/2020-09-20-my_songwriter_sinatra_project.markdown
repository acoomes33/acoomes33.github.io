---
layout: post
title:      "My Songwriter Sinatra Project"
date:       2020-09-21 01:08:38 +0000
permalink:  my_songwriter_sinatra_project
---


If I was to describe building this Sinatra Project, I would have to say it was very... informative to say the least. There were some struggles that I had to work through, and unsuccessful branches that I had to abandon, but I am proud of my product. My project was to create a website that could function as a storage area for songwriters where they can store  songs that are in progress, and complete them when they are finished. For my process, I first built out my app to fit the requirements and to be a MVP. I used the corneal gem to create my file structure, and then I used Sinatra and Activerecord to build out my website and my database structure. For my project I had two models:

* User Model(has_many Songs, and contains a username and a password)
* Song Model(belongs_to a User, and contains a name, artist, genre, lyrics, mood, vibe, bpm, instruments, user_id, and progress(boolean))

A user can sign up, log in, log out, create a new song, edit a song, read specific songs, and delete a song. Using CRUD routes, I was able to complete these tasks. I then set myself towards a stretch goal of including albums, which is where problems persisted for me, especially in the persistence of the data(pun intended).

### Challenges

After finishing the MVP, I set my sights onto the challenge of adding an Album object into the mix, which may have been a little ambitious with hindsight. Creating the table and migrations were fairly simple. but problems arose in the persistence of data. I tried google, github, and other resources, but unfortunately ran out of time. Functionalities such as adding/creating a new song when creating an album deemed troubling, as I worked through pry to find out the corresponding issues in the code. the biggest issue was the relationship between songs and albums. Using Activerecord methods like .save and relationship methods like .album and .songs was one possible solution that I came up with, but it still had a couple of bugs that kept it from a finished project. As much as I would have liked a couple more days, I am still proud of my project and am glad for the experience I gained along the way.
