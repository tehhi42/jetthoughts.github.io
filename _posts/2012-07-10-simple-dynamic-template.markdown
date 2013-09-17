---
layout: post
date: 10-07-2012
title: Simple dynamic template
---

Sometime we need to define some dynamic template before defining variables

One of the solutions:

{% highlight ruby linenos=table %}
string = 'echo #{expr}'  # -> "echo \#{expr}"
expr = 1                 # -> 1
eval("\"#{string}\"")    # -> "echo #1"
{% endhighlight %}

Another way is

{% highlight ruby linenos=table %}
string = "echo %{expr}" # -> "echo %{expr}"
string % {expr: 1}      # -> "echo 1"
{% endhighlight %}
