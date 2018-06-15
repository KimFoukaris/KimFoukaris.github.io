---
layout: post
title:      "Case Management in Rails"
date:       2018-06-15 15:38:52 +0000
permalink:  case_management_in_rails
---

I just finished my Rails project, a Case Management App I developed to help a small NGO I work with track the services it provides to clients.  Since I find that I am most motivated by the opportunity to solve real world problems, working on a case management solution seemed a perfect project.  Fortunately, I received some great advice from the Rails coaches -- focus on the project requirements and keep things simple.  I'm glad that I did because implementation is always tricker than expected and of course I ran into unexpected issues.  

I managed to sail through the first 80-90 percent of the project and was feeling good about the hours and hours of time spent reading through ActiveRecord documentation during the Rails curriculum.  My models, controllers and routes were making sense.  I loved learning about scopes.  But then I hit an unanticipated wall.  I could no longer avoid switching over to a local development environment if I wanted to get my OmniAuth third-party login system working.  As a PC user, I had been avoiding the transition and and it turns out my apprehension was for good reason.  It did not go smoothly.

I was happy to find a thorough Flatiron help post to set up my [Linux VirtualBox](http://help.learn.co/workflow-tips/local-environment/setting-up-linux-virtual-box).  It took some time, but I felt confident that I had downloaded and installed everything according to plan.  Unfortunately, though it all looked good, my virtual machine would not connect, no matter what I tried.  For days, I worked with AAQ, googled for solutions, and was just about to give up.

Finally, I found an [AskAbuntu](https://askubuntu.com/questions/232876/how-to-let-a-virtualbox-guest-running-windows-access-the-internet) post, which explained in clear lanaguage the differences between the recommended "bridged adapter" network and the simpler "network address translation" or NAT.  In short, a bridged adapter gives you a more powerful and flexible network where your virtual machine is essentially made equal to your host machine in terms of the network.  A NAT, on the other hand, basically gives you access to the network through your host machine, not along side it.  Given the pros and cons discussed, I decided to give the NAT a try.  Once I made the switch, I had the NAT network set up and functioning within five minutes.  My network access is probably a bit slower than it would be with a bridged network, but it works and it's still faster than I am at this point!

In terms of the project itself, it was such a pleasure to work with Rails and to begin to see how we can harness the power of the Rails framework.  I feel like I'm finally getting somewher and look forward to our next journey into JS.




