---
layout: post
title: Blocmetrics
thumbnail-path: "img/Blocmetrics.png"
short-description: An analytics and reporting tool that captures event data for registered users.

---

{:.center}
![]({{ site.baseurl }}/img/blocitoff.png)


## Problem

Analytics are important to the life of an application, they allow us to glean insights into user behavior, which helps us improve application quality.   
But how do we create one? Fear not, Blocmetrics is here to help!

## Solution

Blocmetrics is composed of a client-side script snippet that user can embed into their applications, and a server-side API that captures and stores the information. To make this information available to our users, we created a rails application to register the user and display all of its associated applications, as well as the events triggered by the application.
