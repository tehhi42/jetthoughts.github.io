---
layout: post
title: Enable line numbers in Toto syntaxhighlight
author: Michael Nikitochkin
authors_git: miry
date: 04-09-2010
tags: ruby,toto
category: tech
---

  Syntax Highlighting by [Rack::CodeHighlighter](http://github.com/wbzyl/rack-codehighlighter) gem has a bug. May be I did wrong steps. But by default __CodeRay__ disable to show line numbers for code. I did not found any options to enable it by __CodeHighlighter__. So input next lines in __config.ru__ will show line numbers.

{% highlight ruby linenos=table %}
CodeRay::Encoders["html"]::DEFAULT_OPTIONS[:line_numbers]=:inline
{% endhighlight %}
    
  But I have a problem with __css__. I found that __CodeHighlighter__ generate not correct html for __CodeRay__ and default theme's css for Toto broke this highlighting too. You could use my fixed [coderay.css](/css/coderay.css) for Toto.
