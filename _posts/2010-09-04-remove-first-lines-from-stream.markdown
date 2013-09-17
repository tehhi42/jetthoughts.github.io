---
layout: post
title: Remove first lines from stream
author: Michael Nikitochkin
date: 04-09-2010
tags: linux,sed
category: tech
---

I am not a linux hacker, so I wasted a lot of time to find solution to strip first lines from output stream. First my solution was:

{% highlight bash linenos=table %}
tail -f some_file | ruby -e 'a =0; while t=gets; a+=1; puts t if a > 1; end'
{% endhighlight %}

It is looks very long, and I thought that this problem is very popular, and at least one tool already exist in the world.

I knew a tool __sed__ and used it before. So read the manual and wuala:

{% highlight bash linenos=table %}
tail -f some_file | sed "1d"
{% endhighlight %}

Remove first 10 lines:

{% highlight bash linenos=table %}
tail -f some_file | sed '1,10d'
{% endhighlight %}

It do the same thing as first solution, but more clear and simple. __sed__ is a great tool.
