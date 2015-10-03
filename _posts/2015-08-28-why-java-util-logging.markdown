---
layout: post
title:  "Why java.util.logging?"
date:   2015-08-28 08:27:54
category: platform
---
### short version
Why java.util.logging? Because it is included in the JDK.

### long version
I was refactoring a lot of the code base with the goal to get rid of as much dependencies as possible (without sacrificing the feature set). Than I stumbled upon the log4j.jar. I used it because I always used log4j, it was kind of an old habit. For logging purposes, just include log4j and it is done. You can’t do anything wrong with that.

But to reduce dependencies I asked myself what does log4j do, what other logging libraries can’t. I’m sure there are a lot of features included in log4j which other frameworks do not have, but for the trivium project I only used a basic set of logging functionality.

So I started looking around for other logging frameworks with smaller footprints and came across java.util.logging (jul). This one is already included in the jdk, so it doesn’t need anything to work. This got me thinking, if the jdk has its own logging why include a separate framework. After some searching around and countless comparisons of log4j and jul I found that most people just complain about performance.

So comparing scenarios where you write like 1 million log entries in a few milliseconds was important to them (it least it seemed that way). For me that seems like not really relevant comparison. I do not intent to use logging in that way. Further to that I know that most hardware doesn’t even support this kind of usage. So in most real scenarios, the logging gets throttled because of the IO that has to be done.

So regardless of the extra CPU cycles, what else would I miss by changing. Apparently, not much. The log levels are bit different, the logging strings have another format and the API looks different. But all this is just details. No major pain point there.

So I started moving my code base over to jul and got no troubles so far, plus one dependency less.
