---
layout: default
status: publish
published: true
title: "How to fix Google Hangout Screen Sharing on Ubuntu 17.10"
---


After I upgraded to Ubuntu 17.10 I was not able to share my entire screen in Google Hangouts.

![Hangout works again](/assets/images/2017/11/hangouts.png)

This spoiled the upgrade for me.

Fortunately the solution is quite simple: [Wayland](https://de.wikipedia.org/wiki/Wayland_(Anzeige-Server)) is the new default screen server and does not support fullscreen capture.

You can switch back to the XORG screen server: On the login screen click the gear Icon and select "Ubuntu on XORG".

This resolves the issue.