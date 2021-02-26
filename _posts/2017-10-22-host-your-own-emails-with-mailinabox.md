---
layout: default
status: publish
published: true
title: Host your own emails with Mail-in-a-Box
abstract: Setting up your own email server can be quite a hazzle and involves many mooving parts. Fortunately we found Mail-in-a-Box, an awesome open source project, which helps you set up a mailserver in no time.
image: /assets/images/2017-10/mail-in-a-box.png
---

At our cooperative ([TechGenossen](https://techgenossen.de/)) we used Gmail as our Email-Provider at first. But we found GMail too be to expensive for our many members.

So we decided to do our own email hosting.

Setting up your own email server can be quite a hazzle and involves many moving parts. Fortunately, we found [Mail-in-a-Box](1), an awesome open source project, which helps you set up a mail server in no time.

![Mail-in-a-Box](/assets/images/2017-10/mail-in-a-box.png)

> Mail-in-a-Box lets you become your own mail service provider in a few easy steps. It’s sort of like making your own Gmail, but one you control from top to bottom.
 Technically, Mail-in-a-Box turns a fresh cloud computer into a working mail server. But you don’t need to be a technology expert to set it up.
 
 *Source: mailinabox.email*
 
[Mail-in-a-Box](1) features an

* IMAP-Server
* An easy to use Control-Panel
* Nextcloud for contacts
* Roundcube for webmail

It is quite easy to set up on fresh Ubuntu 14.04. machine.

{% highlight bash %}
curl -s https://mailinabox.email/setup.sh | sudo bash
{% endhighlight %}    
The software will guide you through the installation.

All you have to do is change some DNS-Records and voila - it works out of the box.

As the admin of the server you regularly receive emails about how to maintain the box.
 
I am quite happy with the mail server and with the project.

 
[1]: https://mailinabox.email/