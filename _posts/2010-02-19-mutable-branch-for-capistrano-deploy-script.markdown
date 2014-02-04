---
layout: post
title: Mutable branch for capistrano deploy script
date: 19-02-2010
author: Michael Nikitochkin
authors_git: miry
tags: capistrano,ruby
category: tech
---

I always had troubles, when test new feature. I forgot to change branch in capistrano config. So I found one solution wich help me:

{% highlight ruby linenos=table %}
set :branch, `hg branch`.chop || "default"
{% endhighlight %}

or for git:

{% highlight ruby linenos=table %}
set :branch, `git branch | grep '*' | sed 's/^[^a-zA-Z]*//'`.strip || "master"
{% endhighlight %}

{% highlight ruby linenos=table %}
set :branch do
  default_branch = `git branch | grep '*' | sed 's/^[^a-zA-Z]*//'`.strip
  default_tag    = `git tag | tail -n 1`.strip
  tag_or_branch = Capistrano::CLI.ui.ask "Tag or branch to deploy (make sure to push it first) (#{default_branch}|#{default_tag}): [#{default_tag}] "
  tag_or_branch = default_tag if tag_or_branch.empty?
  tag_or_branch
end unless fetch(:branch, false)
{% endhighlight %}

Thats all.
