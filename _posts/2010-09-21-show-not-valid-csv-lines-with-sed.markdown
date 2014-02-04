---
layout: post
title: Show not valid CSV lines with sed
date: 21-09-2010
author: Michael Nikitochkin
authors_git: miry
tags: sed,shell,csv
category: tech
---

I have trouble with invalid formatted CSV file. First step show lines with invalid lines.

{% highlight bash linenos=table %}
sed -n '/"[^",]*"[^",]*"[^",]*",/,1p' <fileName>
{% endhighlight %}

Then find in the google way to replace symbol inside quotes. And read next manual http://sed.sourceforge.net/sed1line.txt. So create a sed script with next content, call it as __script.sed__:

{% highlight bash linenos=table %}
s/\",\"/\$XXXX\$/g;
:a
s/\([^,]\)"\([^,]\)/\1'\2/g
ta
s/\$XXXX\$/\",\"/g;
{% endhighlight %}

Next we just do:

{% highlight bash linenos=table %}
sed -f script.sed <fileName>
{% endhighlight %}

And we get in output a normal csv format file. Next we just add the argument to apply this in this file.

{% highlight bash linenos=table %}
sed -i .bak -f script.sed <fileName>
{% endhighlight %}
