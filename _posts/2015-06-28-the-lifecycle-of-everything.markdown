---
layout: post
title:  "the lifecycle of everything"
date:   2015-06-28 16:44:54
category: platform
---
### Type
A type has no lifecycle. Since it is a type Definition it will be used for data instantiation.
Types cannot be loaded or unloaded. Either they are known (in the classpath ) or not.

### Task
The life cycle of a task is completely controlled by the platform. The developer cannot instantiate or destroy a task.
The platform will instantiate tasks whenever and wherever needed. So even the enclosing JVM will be determined at runtime. It is therefore crucial that the task has no direct dependency on any shared objects. Sharing objects between task is therefore not allowed.

### Binding
The life cycle of a binding can be controlled by the user. The user can start and stop a binding.
To disable a binding completely (undeploy) you have to remove the code from the platform. As long as the extension is loadable it also is startable.
