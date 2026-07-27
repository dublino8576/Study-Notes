# AWS vs Heroku

AWS and Heroku are both services aimed at running our web apps 24/7, so that they can store data, process data, and run software.

However, the very first main distinction is that Heroku is a **PaaS (Platform as a Service)**, while AWS is an **IaaS (Infrastructure as a Service)**.

This means that Heroku handles the network connections, provides servers and solves security configurations for you (it is a *fully set-up platform*), while AWS only provides the *raw infrastructure* (building blocks), such as providing individual servers, databases and firewalls, but leaving the configuration and connection of these building blocks to you.

## Drawbacks of using PaaS: 
In my previous YogaLane full-stack booking platform I deployed on Heroku I noticed how relatively quick was using this cloud service, but it had its own limitations.
Namely, Heroku databases would not save dynamic assets when reloading a new session on the platform, which led to having to use Cloudinary to be able to save dynamic assets (profile pictures for each yoga student dashboard). The developer is basically bound to the restraints posed by the platform. 
