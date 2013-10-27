---
layout: post
date: 10-07-2012
title: Simple dynamic template
author: Michael Nikitochkin
tags: ruby,strings,metaprogramming
category: Tech
---

Sometime we need to define a dynamic template before defining variables used in the template.
Let me show few examples to solve this problem in Ruby.

The best way is to use the [format string features from the Ruby](http://ruby-doc.org/core-2.0.0/String.html#method-i-25):

{% highlight ruby linenos=table %}
string = "echo %{expr}" # -> "echo %{expr}"
string % {expr: 1}      # -> "echo 1"
{% endhighlight %}


First method is based on ability to evaluate the Ruby expression in string:

{% highlight ruby linenos=table %}
string = 'echo #{expr}'  # -> "echo \#{expr}"
expr = 1                 # -> 1
eval("\"#{string}\"")    # -> "echo 1"
{% endhighlight %}
