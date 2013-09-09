---
title: Shell access
---

# Shell access

## SSH

cXXs.freistilbox.net is your own shell server. Every site is represented
by its own user on this host.

After logging in with

    ssh s123@cXXs.freistilbox.net

you will get access to a copy of your complete site environment,
including a [checkout of your document root](/basics/filesystem/) as well as access to your
[shared folders](/basics/boxfile/) and [prepared configuration files](/basics/includes/).

In the directory `current` will find a identical copy of what the
webservers are using. The currently active deployment of you web
application resides in `current/docroot`.


## SFTP

With the same user you can access your site using SFTP to transfer files
from and to your web application.

Your public shared files can be accessed in the directory you defined in
your [Boxfile](/basics/boxfile/), relative to the directory
`current/docroot` on the shell host.

Your private shared folders can be found in `current/private`.
