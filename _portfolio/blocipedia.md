---
layout: post
title: Blocipedia
thumbnail-path: "img/Blocipedia.png"
short-description: Build a production quality SaaS app that allows users to create their own wikis.

---

{:.center}
![]({{ site.baseurl }}/img/blocipedia.png)


## Problem

Have you ever looked at Wikipedia and think I can make a better one AND charge money for it? Look no further than Blocipedia, where when you add some cool functions like collaborator and make some wiki articles private, you can charge people for it! Let's get to the making of the money forthwith.  

## Solution
First we want to build an authentication system, which we built with the handy-dandy Devise authentication engine that generates all the necessary components we need to sign in and out of the application.     
To make money, we need to make things exclusive. We first create a pricing chart to get users to pay for premium features. (think money)  
From there on, add a role column to your users, all users can be 'standard' (default - those who live in poverty), or 'premium' (think dollar sign), and of course, to ensure your reign of terror rests firmly in your hands, create an admin role.  
All premium users are free to view privately created wikis, on top of that they can also collaborate/collude with their equally wealthy friends. To overcome the challenge of adding the collaborator feature, we organized the relation to be has_many_through to reduce complexity. 
 
####If you're wondering if we profitted or not, just take a good look at our $5 million mansion in Beverly Hills.