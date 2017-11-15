---
title: Headed to RubyConf! -
date: 2017-11-14
tags: ruby, friends, conferences
---

Taking a few moments on the flight to New Orleans to write a bit about the upcoming conference.

# I AM SO EXCITED! 

I realize that there are going to be many ruby friends to meet up with once we're in New Orleans, but I was not expecting the vast number of Ruby friends on the flight with Jer and I today.  They include Sam, Renee, Aja, Ryan, a couple of Ada Alumni folks. This is going to be an overwhelmingly great time.

The conference subject matter is going to be incredible. This will be the first time, I think, that I will be listening to Matz in person. Pretty exciting stuff. And while I have seen Sandi Metz speak in person before, I'm highly looking forward to catching her upcoming talk here at the conference. I'm a big fan of the way that she outlines her subject matter in a measured, approachable way. Her talks carry along strong, consistent themes of inspiration - that you can do The Thing if you perservere. 

Y'all - that conference talk in Paris about the bicycling trek? Amazing. One of my top 5 favorite tech conference talks of all time.

I'll need to sit down with the schedule tonight and outline the docket of what to see. I'm a bit conflicted on what I'd like to focus on: 

- "Work Stuff": Themes relating to CI/CD, configuration management
- "Curiousities": Stuff that I have a strong interest in that isn't the current nine-to-five gig

Really, I think there's a strong possibility that I'll end up doing the latter. There's a number of reasons for this - Giving my brain a break from intense work focus, thinking about problems in a different way, exploring things that may be of greater long term value (value can be anything from personal satisfaction or great work skills in the back pocket.)

# The Flight to New Orleans - Random Observations

When flying domestically, we fly Alaska, or sometimes Southwest Airlines.

There's lots of reasons why - Alaska's food/bev selections are great, they participate in recycling, and they aren't trying to constantly pitch their brand to you. (United and Continental airlines are particularly bad in this regard. The one and only time I've ever flown with Continental, they aired self-promoting minutes-long commercials on takeoff and landing, AND at the gate via their own television displays.)

One of the other keen features of Alaska is that they offer in-flight internet via GoGo. It's a great option if you happen to be on a longer flight.

*The above statement is not true if half the folks on the plane are technologists who are going to the same tech conference. ;-)*

Because the network is pretty damned saturated, I've been playing around a bit with the paywall in order to figure out how it works. This includes doing traceroutes on the gogo domain versus other domains (under the context where I don't have a cookie or token to bypass the paywall.)

What's curious about trying to access other websites in this state is that there's 3 resultant behaviors for attempted access via a web browser:

1. The web address never resolves
2. The web address results in a redirect to the purchase page for the GoGo paywall
3. The web address is not blocked at all and you are able to freely access it

Now, like me you're probably making the assumption that if you haven't paid for the wifi service that 100% of websites should never resolve.

You'd be wrong.

Here are the test results from my exploratory testing during this flight (11/14/2017):

## Never Resolves

- twitter.com
- facebook.com

## Redirect to Paywall

- instagram.com
- disney.com
- craigslist.com
- google.com
- yahoo.com
- cnn.com
- skymall.com

## Webpage Resolves!

AMAZON.COM 

This revelation is so gross. 

The behavior likely means that amazon.com and GoGo have some sort of partnership (likely Amazon pays GoGo or Alaska $$$$$) to bypass the paywall entirely. This likely means that other companies have also given the proverbial wink (and some payment) to GoGo to do the same.

I wish I had a prep list of common domains before hopping on this flight - discovering more information about the behaviors via ad-hoc testing is pretty fascinating to me.




