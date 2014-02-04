---
layout: post
title: Different timestamp for Rails and Postgres
date: 16-09-2010
author: Michael Nikitochkin
authors_git: miry
tags: time,spec,db,postgres
category: tech
---

Today I found a discrepancy in Rails timestamp and Postgres timestamp for my specs:

{% highlight ruby linenos=table %}
puts Time.now.to_iputs ActiveRecord::Base.connection.execute("SELECT LOCALTIMESTAMP as c1")[0]["c1"].to_time(:local).to_i
{% endhighlight %}

But for console timestamps are the same. Why it is not working for specs, I dont know.
