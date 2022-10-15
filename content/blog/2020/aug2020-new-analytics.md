---
title: "New Analytics"
date: 2020-08-23T11:16:15+02:00
draft: false
description: "Today, I wanted to talk about the analytics I put on my website (and by extension on my blog)..."
---

Greetings everyone!  
Today, I wanted to talk about the analytics I put on my website (and by extension on my blog).

First off, I added some analytics by curiosity, to know how much people read my blog posts and where does they come from (referer) and the country they are from.  

I tested two solutions for analytics in the past month:
 - [GoatCounter](https://goatcounter.com)
 - [Plausible](https://plausible.io)
 
I didn't tested Matomo since this solution is too complex for what I want to achieve, I need something simple, self-hostable easily and very light.  
You can see more alternatives to Google Analytics on [Reverse Eagle's developper website](https://developers.reverseeagle.org/replace/google-analytics/).

I chose GoatCounter and Plausible since they have all the criteria I required:
 - Very easy to use
 - Very easy to deploy (either Docker or really easy installation)
 - Clear interface with no useless options (in my case of usage)
 - The stats can be publicly viewed
 
Now, let's compare the two shall we?

#### The installation

GoatCounter must be the easiest to setup and get running, as it is basically a static executable (written in Go), you just need a simple `./goatcounter` to start it.  
My current command to launch GoatCounter is `./goatcounter serve -listen 0.0.0.0:8080 -tls none` so GoatCounter listens on the local port `8080` so it can be used with a reverse proxy (more on that later). If needed, Goatcounter can get TLS certificates but I would recommend staying with a reverse proxy as I *personally* feel this is much more practical.  

On the other hand, Plausible uses Docker to work and provides an already [nice-looking docker-compose.yml file](https://github.com/plausible/analytics/blob/master/docker-compose.yml).  
You just have to pay attention so you don't miss the initial admin setup, otherwise it's still really easy to deploy.

#### Adding a website

As said earlier, GoatCounter is a static executable.  
To add a website, it is easy as `./goatcounter create -domain stats.domain.tld -email email@domain.tld` and the setup will automatically ask for a password.  
Now, all you have left to do is to point the dns of `stats.domain.tld` to your GoatCounter server and you're all set!  
Just include the Javascript script in your `<head></head>` and you can start.

On the other hand, in Plausible, you just have to hit the big '+ Add a website' button, fill the form and here you go, you get the code to add in your `<head></head>`.  
> /!\ I didn't figured how to add custom domains for Plausible yet (self-hosted), I'll keep you informed on that.

#### Viewing the stats

Both solutions have a really nice web interface but I must say, Plausible's is my favorite.  

The interface of GoatCounter is very simple and offers lots of informations very efficiently and offers even more by clicking on the charts.  
On the other hand, Plausible offers a really refined interface but with less options, it however shows a really nice map of all the visitors and a real-time counter of how much visitors there is on the website.

---

In the end, I settled on Plausible for my own website as *said earlier* the interface is much more refined.  
I'll soon make a post about what web server I use as a reverse proxy for the appps I host and why it is so cool so stay tuned!    

I hope you liked this post, if you did, don’t forget to subscribe to this blog through RSS.  
I'll see you next time!