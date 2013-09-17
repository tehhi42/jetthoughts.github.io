---
layout: post
title: Jruby and Spork
date: 13-04-2010
author: Michael Nikitochkin
tags: jruby,spork
category: tech
---

When you try run spork you have to enable fork for spork (instead you will have error
`spork/forker.rb:18:in `initialize': fork is unsafe and disabled by default on JRuby (NotImplementedError)`). So it should like:

{% highlight ruby linenos=table %}
jruby -J-Djruby.fork.enabled=true <path-to-jruby-binaries>/spork
{% endhighlight %}
