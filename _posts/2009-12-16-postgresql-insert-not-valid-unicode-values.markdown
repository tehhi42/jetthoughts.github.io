---
layout: post
title: Postgresql Insert not valid unicode values
date: 16-12-2009
author: Michael Nikitochkin
authors_git: miry
tags: rails,postgresql,ruby
category: tech
---

I have an error when try insert to DB charcters not valid for Postgres in Rails application:

{% highlight ruby linenos=table %}
PGError: ERROR:  invalid byte sequence for encoding "UTF8": 0x92
{% endhighlight %}

Found solve, but not pretty cast all string to UTF-8 with valid characters by Kconv:

{% highlight ruby linenos=table %}
Kconv.toutf8("string with invalid characters \x92")
{% endhighlight %}

0x92 it is Word's quotes in Windows-1250 or Windows-1252 encoding.
So next method is: `Iconv.new('UTF-8', 'Windows-1250').iconv(text)` resolve this issue.

P.S: When I search about answer on this question, I found next method to clear not unicode symbols: `Iconv.new('UTF-8//Ignore', 'UTF-8').iconv(product_line)`
