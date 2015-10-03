---
layout: post
title:  "Versioning"
date:   2015-10-03 14:47:54
category: platform
---
I recently came to the topic of versioning. I’m not a big fan of versioning since I almost always see people who disregard their own versioning strategy after a certain amount of time. But lets take a step back on that one.

Close to all projects today have adopted semantic versioning as their versioning strategy. If you read the strategy behind it, it all sounds very reasonable and the concept seems not too far fetched.
In practice, especially in corporate environments, versioning usually becomes a big mess, when other “stuff” becomes more important. For example, if you need a patch that brakes thing, you are violating the semantic versioning strategy, but the customer has priority.
The same goes for “we need a new feature release to sell something”. In that case too, version numbers jump, just because it is convenient. And as I said before I saw a lot of those kind of reasons why versioning went completely awry over time.

Than I came across an article about [sentimental versioning](http://sentimentalversioning.org/). It basically states that we should version software by our own standards, set by the creator of the project. Often this leads to a different perspective in versioning, which by itself doesn’t have to be bad.

So keeping this in mind, I tried to find a different way of providing versions.

Since versions are only markers in time which describe a certain working feature set, I started to ponder, what actually would happen, if we completely build a version number from time and not some spec sheet.
After that, the geek in me kicked in and tried to find some cool way to build versions out of time without going back to “that build from Thursday 1st October 2015”, because that is obviously too long to communicate.

So lets start with version 0 - everything has to start somewhere.

Version 0 is set to timestamp 1444000000 (so Sun, 04 Oct 2015 23:06:40 GMT human time).

After that, the version increases constantly ever 2^21 seconds.
In the human world that would be about every 24 days.

So far there are no subversions. The criteria for defining an increment would be to cite the git commit hash (abbreviated version preferred).

So on christmas 2015 we will have version 3.

That is one hell of a predictable system. Now I only have to figure out, what the feature set of that release is actually gonna be.
And of course I [build](http://www.tvm.io/version.html) a countdown to the next release.
