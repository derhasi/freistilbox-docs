---
title: Shell access
---

# Shell access

## SSH

Each freistilbox cluster has its own shell server, independent of the web application boxes on which your application runs. The shell server's hostname is `cNNs.freistilbox.net` where "NN" is the numeric ID of your freistilbox cluster, for example `c42s.freistilbox.net`.

Every application instance on your cluster has its own user account, for example `s123`.

With your instance ID, you can log in like this:

    ssh s123@c42s.freistilbox.net

This gives you access to a copy of your complete site environment, including a [checkout of your document root](/basics/filesystem/) as well as access to your [shared folders](/basics/boxfile/) and [prepared configuration files](/basics/includes/).

In the directory `current` will find a identical copy of what the webservers are using. The currently active deployment of you web application resides in `current/docroot`.


## SFTP

With the same user you can access your site using SFTP to transfer files from and to your web application.

Your public shared files can be accessed in the directory you defined in your [Boxfile](/basics/boxfile/), relative to the directory `current/docroot` on the shell host.

Your private shared folders can be found in `current/private`.
