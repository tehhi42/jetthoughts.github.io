---
layout: post
title: Show time string in different locale in Rails
author: Michael Nikitochkin
date: 2010-01-03
tags: ruby,i18n,rails
category: tech
---


I am a russian and use native locale settings, but some times, I need parse date. In Rails 2.3 method date to string return in native locale. So when I tried parse date in JS example, I have a error. Read about I18n and found answer.

{% highlight ruby linenos=table %}
I18n.l(Time.now, :locale => 'en')
{% endhighlight %}

It is return datetime in rfc832 format, which used in JS too.
