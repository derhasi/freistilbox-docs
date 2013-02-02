---
title: Checkout
---

# Checking out the site repository

Since Git uses a distributed approach, you're going to create a local copy of the central repository. Changes to your web application code will first be made (and hopefully tested) in this local copy and then, at a reasonable point in time, transferred to the central repository on the freistilbox hosting platform. Within seconds, the webserver(s) will be updated from the central repository and your changes become visible on the Web.


## Clone the central application repository

Let's create your local website repository. You need to connect to your central application repository using your SSH key.

Each website has its own Git repository URL as follows:

    ssh://SITEID@repo.freistilbox.net/~/site

For example:

    ssh://s123@repo.freistilbox.net/~/site

With the following command, you create a working copy of the application repository on your workstation (of course, you'll have to replace the instance details):

    $ git clone ssh://s123@repo.freistilbox.net/~/site site123
  
This command will create a directory `site123` containing a copy of the central repository. This local clone will have a connection to its original so you can easily update your local copy from the central repository and transfer your local changes back to the freistilbox platform.


## Excluding files from the repository

From the file `.gitignore`, a hidden file in the root directory of the repository, Git reads a list of names and patterns for files that you don't want to have added to the repository. For example, since you don't want put backup files under version control, you can add the pattern `*.bak` in a separate line to `.gitignore`. 

Another important exception are the asset directories like `sites/default/files`. You have to make Git ignore all possible multisite directory names by using a pattern as described below.

We recommend you also exclude `settings.php`, especially if you want to do a staging workflow with separate website instances. On the freistilbox hosting platform, you can use a different configuration file for each staging instance, for example `settings.production.php` and `settings.staging.php`. Even if you don't intend to do staging, simply use `settings.production.php`.

So, make sure that `.gitignore` contains at least these lines:

    sites/*/files
    settings.php
