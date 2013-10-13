---
layout: post
title: "Taken from shell-fu"
---

This is taken from shell-fu.org still a pretty handy one liner though

{% highlight bash %}
aptitude search ~c | awk '{ print $2 }' | xargs aptitude -y purge
{% endhighlight %}

This will delete any packages that are not installed anymore which still has configuration files on the box
