---
layout: post
title: "Git configs"
---

Because  I never seem to remember them

Global git ignore
{% highlight bash %}
echo ".DS_Store" >> ~/.gitignore
git config --global core.excludesfile ~/.gitignore
{% endhighlight %}

My info
{% highlight bash %}
git config --global user.name "Your Name Comes Here"
git config --global user.email you@yourdomain.example.com
{% endhighlight %}

Colorized outputs
{% highlight bash %}
git config --global color.branch auto
git config --global color.diff auto
git config --global color.interactive auto
git config --global color.status auto
{% endhighlight %}
