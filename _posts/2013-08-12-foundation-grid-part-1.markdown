---
layout: post
title:  "Foundation grid. part 1"
date:   2013-08-13 10:00:00
categories: hello welcome new
---

# Grid

Create powerful multi-device layouts quickly and easily with the 12-column, nestable Foundation grid. If you're familiar with grid systems, you'll feel right at home. If not, you'll learn quickly.

## Using our Predefined HTML Classes

These are examples of different ways to use the Foundation Grid. Foundation uses box-sizing: border-box so that borders and padding do not affect the overall width of the columns, making the math dead-simple. Since Foundation is mobile-first, we'll stack content by default. You do have access to an entirely separate small grid to use up to the 768px breakpoint. This means you can create some pretty complex layouts and even drop columns if you want.
{% highlight html %}
<div class="row">
  <div class="small-2 large-4 columns">...</div>
  <div class="small-4 large-4 columns">...</div>
  <div class="small-6 large-4 columns">...</div>
</div>
<div class="row">
  <div class="large-3 columns">...</div>
  <div class="large-6 columns">...</div>
  <div class="large-3 columns">...</div>
</div>
<div class="row">
  <div class="small-6 large-2 columns">...</div>
  <div class="small-6 large-8 columns">...</div>
  <div class="small-12 large-2 columns">...</div>
</div>
<div class="row">
  <div class="small-3 columns">...</div>
  <div class="small-9 columns">...</div>
</div>
<div class="row">
  <div class="large-4 columns">...</div>
  <div class="large-8 columns">...</div>
</div>
<div class="row">
  <div class="small-6 large-5 columns">...</div>
  <div class="small-6 large-7 columns">...</div>
</div>
<div class="row">
  <div class="large-6 columns">...</div>
  <div class="large-6 columns">...</div>
</div>
{% endhighlight %}