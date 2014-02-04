---
layout: post
title: Change size of images shell script
date: 17-05-2010
author: Michael Nikitochkin
authors_git: miry
tags: shell,imagemagick
category: tech
---

I had a issue: Find all images in directory and change size to "150x200". So lets start.

1. Find all images **find .**
2. Convert size of image: **convert -geometry '150x200' image.gif image.gif**

{% highlight ruby linenos=table %}
for i in $(find .)
do
  convert -geometry "150x200" $i $i
done
{% endhighlight %}

If you want get only image size use: *identify image.png*
