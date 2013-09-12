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

In the directory `current`, you will find a identical copy of what the application boxes are using to run your website. The currently active deployment of your web application always resides in `current/docroot`.

<span class="label label-warning">Warning</span> During deployment, the `current` directory will change. When you need to update your application while you work in a shell session, make sure to `cd` into `current` again.


## SFTP

Using the same user account, you can also access your website's asset files via SFTP. This enables you to transfer files from and to your web application.

Your public shared files (directly available to external HTTP clients) can be found under `current/docroot`, in the directories you defined as shared folders in the [Boxfile](/basics/boxfile/).

Your private shared files (only available to your application) can be found in `current/private`.
