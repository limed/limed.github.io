---
layout: post
title: "Changing permissions for all directories in folder"
---

Ever run into a situation where you have a mixture of both files and folders in a directory and you only need to change the permission of the folder? Naturally the first thing that comes to mind is to do something like this

{% highlight bash %}
    find . -type d -print | xargs chmod 755
{% endhighlight %}

But what happens if your folders have spaces? Using find that way will not escape the spaces instead the solution to this is to use find but in a slightly different manner

{% highlight bash %}
    find . -type d -print0 | xargs -0 chmod 755
{% endhighlight %}

The -print0 tells find to terminate with zero so that whitespaces are recognized and the same goes for xargs as well.
