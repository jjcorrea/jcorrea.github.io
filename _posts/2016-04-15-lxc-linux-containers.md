---
layout: post
title: LXC - Linux Containers
---



The [LXC](https://linuxcontainers.org/) project, formerly LinuxContainers*, is an open source implementation of a relatively recent hype, an isolation paradigm so called OS level virtualization. 

The overhead caused by working with Virtual machines required a better abstraction due to the penalties involved in maintaining, in terms of simplicity, performance, so this initiative aims to provide better and simpler isolation mechanisms (special thanks to Linux kernel).


> Our main focus is **system containers**. That is, containers which offer an environment as close to possible as the one you'd get from a VM but without the **overhead** that comes with **running a separate kernel** and **simulating all the hardware**.


> This is achieved through a combination of kernel security features such as **namespaces**, mandatory access control and **control groups**.

> (LinuxContainers.org)

### The first Production-ready release

LXC's very first release came with Kernel 2.6.32 (2009), and approximately 5 years later came the first self-entitled "production-ready" release: LXC 1.0.0 (Feb 2014).


### Outline

The general idea around OS level virtualization is to provide lighter mechanisms for creating and maintaining multiple **isolated environments** per host. The isolation comes in two flavors:

1. **Resource isolation**: Part of a properly isolated environment involves isolating it in terms of resources. You should be able to dedicate part of your computer's capabilities (CPU, Memory, I/O) for use in a specific process, or to balance your resources according to its specific needs. Linux kernel provides [CGROUPS](https://wiki.archlinux.org/index.php/cgroups) which are used by LXC for doing so.


2. **Security isolation**: The second important piece of properly isolated units are the security constraints. As well as the cgroups work on resource isolation, the kernel also provides [NAMESPACES](http://man7.org/linux/man-pages/man7/namespaces.7.html) for keeping the necessary isolation on the processes level.


### Templates

Creating a container generally involves a set of per-distribution actions, as each of those often requires tools which may not be available for other distros. LXC templates are shipped with lxc and include templates for creating containers for several different distributions.


### Examples

Creating a simple container

<pre class="message">
$ lxc-create -t ubuntu -n testcontainer
</pre>

Displaying container status
<pre class="message">
$ lxc-info -n testcontainer
</pre>

Starting container
<pre class="message">
$ lxc-start -n testcontainer
$ lxc-info -n testcontainer
Name:		testcontainer
State:		RUNNING
PID:		1689
IP:			10.0.3.146
...
</pre>

### Footnotes

* LXC isn't the only project below the LinuxContainers umbrella nowadays, it includes [LXD](https://linuxcontainers.org/lxd/introduction/) and [LXCFS](https://linuxcontainers.org/lxcfs/introduction/).


### References

* [Ubuntu LXC Documentation](https://help.ubuntu.com/lts/serverguide/lxc.html#lxc-templates)
