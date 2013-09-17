---
layout: post
title: Allow multiple access control requests for Rails
date: 22-12-2010
---

If you have problem with sending XHR requests from different domains, you find trouble to get content, because

{% highlight bash linenos=table %}
XMLHttpRequest cannot load http://different.domain.local:3000/visits. Origin http://localhost:3000 is not allowed by Access-Control-Allow-Origin.
{% endhighlight %}

The solution is to setup response headers: _Access-Control-Request-Method_, _Access-Control-Allow-Origin_.

{% highlight ruby linenos=table %}
headers['Access-Control-Allow-Origin'] = '*'
headers['Access-Control-Request-Method'] = '*'
{% endhighlight %}

Example for rails:

{% highlight ruby linenos=table %}
#app/application_controller.rb
after_filter :set_access_control_headers
def set_access_control_headers
  headers['Access-Control-Allow-Origin'] = '*'
  headers['Access-Control-Request-Method'] = '*'
end
{% endhighlight %}


You can look to sources of the sample Sinatra application in [GitHub](https://github.com/miry/cross-domain-sharing).
Demo live in
[Heroku](http://cross-domain-ajax-request.herokuapp.com/index.html).
Or use [these smaples](https://gist.github.com/miry/5447203).
