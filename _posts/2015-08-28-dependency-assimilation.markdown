---
layout: post
title:  "dependency assimilation"
date:   2015-08-28 10:27:54
category: platform
---
I recently had to show somebody the current state of the trivium project, because there was a bug that I couldn't solve on my own.
So the first thing was, establish a working environment on his PC.
The setting up process took quite some time and needed a lot of downloads to actually achieve a basic runnable system. Quiet unhappy with this development I tried to bring the boostrapping process down to a minimum effort.

### situation before
I build a core project which hosts all my code in a single repository. All the needed libraries are added as jar file. Up to this point I tried to place separate dependency jars into its own module (intelliJ modules or eclipse projects) within the workspace.
The reasoning behind this was, if I wanted to upgrade one functional dependency I could exchange this project und do not have to touch all dependencies. To state this upfront, I am aware of maven and initially started using it. The problem with that approach was, that dependencies had other dependencies which then lead to complete mixed up tree of jar files with conflicting versions in between. The only solution to that was, doing manual resolution and hand pick all jar files and versions.

### emerging problems
So combining all this I had a project running in my environment, but the complexity increased with every new dependency. Bringing the whole system to a new environment (server or even a second developer) was a really cumbersome process. Getting this thing running on a server was close to impossible without cloning all github repos mixing them together and then apply the startup script.
This wasn't gonna fly anywhere if I continued that path.

### my solution - dependency assimilation
What I mean by that is, whenever I have a dependency necessary to bootstrap the engine, the source code get incorporated into the trivium code base.

This of cause has some drawbacks like:

* upgrades are complex
* library license has to be conform with trivium license (and the other way around)
* the codebase for trivium gets huge

But on the other hand, now all I have to do to get an engine running is to checkout the core repository and click start, regardless of IDE or environment.
As for the server runtime, it can all be easily packaged in one jar file and make it executable, no start parameter or classpath configuration required.

To be totally honest, this only worked fine for me, because I drastically reduced the dependency footprint to a minimum. So right now I only had to assimilate about 4 libraries.
With more dependencies the process would probably be more challenging, but this way you question the need of all of your dependencies twice.
