---
layout: default
status: publish
published: true
title: Script to disable internet connectivity for Mac OS X
---
From time to time I really want make it hard for me to seek for distractions.

I found myself using the nice Mac OS X tool [Freedom](http://macfreedom.com/) all the time. Freedom disables the network connectivity, which means no Twitter, Facebook etc.

But when I revisited the site I found that the author now charges 10$ for it - Thats just a little bit to expensive in my opinion.

So I went out and it took me 5 minutes to come up with freedom.sh.

{% highlight bash %}
#!/bin/bash
echo "Enough of this filthy internet" | cowsay -s
sudo route -n delete default &> /dev/null
{% endhighlight %}

[Cowsay](http://en.wikipedia.org/wiki/Cowsay) required. (If you don't want to install cowsay just remove the line!)

    ________________________________
    < Enough of this filthy internet >
    --------------------------------
               ^__^
               (**)_______
                (__)       )/
                 U  ||----w |
                    ||     ||

To reenable your internet you have to add back the default route or restart your computer.