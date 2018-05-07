---
layout: post
title:      "Volunteer Management Sinatra App"
date:       2018-05-07 05:52:46 +0000
permalink:  volunteer_management_sinatra_app
---


For past year, I’ve been volunteering with a small aid organization that helps refugees and migrants adjust to life in their new home country.  One of the areas that we struggle with is how to more effectively organize and manage volunteers.  Inspired to alleviate those struggles, I created a Volunteer Management Sinatra App that keeps track of volunteers and the tasks that they have agreed to manage.  

Though I felt much more confident than I did during my CLI Data Gem project, I did run in to several hurdles and learned a lot as a result.  In this post, I’ll explain where I ran into trouble and how I worked through the issues in the hope that it might save someone time and frustration in the future.

#### Hurdle 1 - Remembering how to use GitHub when not in a Learn IDE lab

The Learn IDE is a wonderful tool, but during this project I realized that yet again it had lulled me into thinking that I was GitHub savvy.  The truth is, I still get confused when I want to use GitHub outside a Learn IDE lab.  To get my project started, I had to refresh my memory and read through several tutorials.  Even then, I had two or three false starts because I initially set up my repository while in the assessment lab.  This is not a great idea. 
The solution was really very simple to implement.  

1.  Create a new GitHub repository.  Give it a name, make it public and add a README.md.
2.  Open the Learn IDE, and then open a New Window from File.
3.  Delete the sandbox.
4.  Clone with the SSH key from the command line:  git clone “SSH key”
5.  Change directory
6.  When ready, git add ., git commit -m “message”, and git push -u origin master to save your changes to GitHub.

#### Hurdle 2 – Model Name Choice

For my volunteer management app, I had originally planned to use three models:  User, Volunteer and Activity.  However, because ActiveRecord automatically pluralizes for you, my activities_controller wasn’t recognized (nouns that end in y are problematic).  Although there is documentation to override the automatic pluralization in ActiveRecord, I chose to rename my Activity model Task since it was just as meaningful and easier to use in ActiveRecord.  I had to rewrite my Task model and migration, as well as reset the database using rake db:reset.

#### Hurdle 3 – Conquering ActiveRecord Associations

ActiveRecord Associations are powerful and save a lot of time once you fully understand them.  Unfortunately, the ActiveRecord magic that is so powerful can be confusing for a newcomer.  When I began this project, I still had the tendency to assume that my models and migrations had done all the heavy lifting and all I had to do was create a Volunteer and assign it a user_id to complete the association.  Of course that’s not the case, as we had learned earlier in the program.  

I quickly realized that something was wrong when shotgun produced errors when I tried to display the volunteers and tasks.  I used Tux to help me identify that though I was creating volunteers, they remained unassociated with their users.  I reread the ActiveRecord Associations documentation but was unable to pinpoint my problem.  My models and migrations were fine.  The associations were set up properly.  I finally found a wonderful tutorial, which describes in detail the model, migrations, instantiation relationships and it finally clicked for me.  I used the code user.volunteers.create(params) to create and associate at the same time, rather than creating the volunteer, defining the association and then adding the volunteer using user.volunteers << volunteer.

For me, the value of these projects is very real.  When forced out of the Learn IDE comfort zone, I surprise myself.  Occasionally, I’m disappointed that it still takes me time to think things through and find solutions to the problems that I encounter.  But the sense of accomplishment when I realize that I’ve finally mastered the concepts far outweighs the frustration.  Of course, I’m also reminded that there is so much more to learn!

