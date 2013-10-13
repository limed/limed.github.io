---
layout: post
title: "Mail log fu"
---

Ever had someone go "I need you to look through the logs and get me every email address this From address sent to". Well heres how (or at least the easiest way I can think of doing it)

{% highlight bash %}
grep "from=<foo@example.com>" /var/log/mail.log | awk '{if ($6 != "NOQUEUE:"){print $6}}' | sed 's/\://g' |\
while read SEARCH; do grep "${SEARCH}" /var/log/mail.log; done | grep "to=" |\
awk '{print $7}' | sed -r 's/^to=<(.+)>\,$/\1/g' | uniq
{% endhighlight %}

Here is a step by step walkthrough of whats going on

1. We grep the from address out of the mail log
2. Pipe the output to awk and get the 6th column which is the mail id, if the 6th column doesn't start with ```NOQUEUE``` print the output
3. The output goes to sed which removes the ":" and
4. Read the output and put it into a variable and from that variable go through the mail log again
5. This time filter out the ```"to="``` line from the mail log and print out the 7th column (which is the to address)
6. Use sed to filter out the ```to=<>``` line to print out the actual email addresses
7. Pass it through uniq to make sure there are no dupes

