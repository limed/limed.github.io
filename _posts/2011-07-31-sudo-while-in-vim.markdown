---
layout: post
title: "sudo while in vim"
---

Ever had a time when you opened a file in vim and edited a bunch of stuff without realizing that its read-only, well this solves you from exiting out of the file and reopening the file with sudo

{% highlight bash %}
:w !sudo tee %
{% endhighlight %}
