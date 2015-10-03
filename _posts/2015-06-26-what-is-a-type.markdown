---
layout: post
title:  "what is a type"
date:   2015-06-26 08:13:54
category: type
---
A type is abstract definition of aa data structure. Types can be serialized to different representation. By default, every Type is available as JSON, XML and JavaType.

At first Types can only be defined in Java.
Later lazy types will be build incrementally from existing data. So the need to define a type will lessen and the system can learn new elements on its own.

So how does it look.
Types are extensions to the trivium system, so they must be package in the appropriate java package.
All extensions must also implement SPI for dynamic loading and unloading. SPI is implemented by package a service metafile into the jar file, so the JVM knows, what service will be extended by this implementation.
Although it is called service, trivium uses this system only to load class definitions. It makes no assumptions on the type of implementation.

This would be a simple type.
{% highlight java %}
{% endhighlight %}
