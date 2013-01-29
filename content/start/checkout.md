---
title: Checkout
---

# Checking out the site repository

With this command, you can create a clone of the website instance on your workstation:

    git clone s123@repo.freistilbox.net:site site123


Since Git uses a distributed approach, you're going to create a local copy of the central repository. Changes to your Drupal installation will first be made (and hopefully tested) in this local copy and then, at a reasonable point in time, transferred to the central repository on the DrupalCONCEPT hosting platform. Finally, the webserver(s) will be updated from the central repository and your changes become visible on the Web.

For customers that are new to Git, we've prepared this introduction: [Git Basics](/git/git-basics/)


## Clone the central DrupalCONCEPT repository

Let's create your local website repository. You need to connect to your central DrupalCONCEPT repository via HTTPS using the following credentials:

* `hostname`: The main hostname of your DrupalCONCEPT server or cluster
* `siteid`: The ID of your DrupalCONCEPT website instance
* `username`: The Git login username of your website instance
* `password`: The Git login password of your website instance

The Git URL is composed of these parts as follows:

    https://<username>:<password>@<hostname>/git/<siteid>

For example:

    https://site007:s3cr3t@pro01.drupalconcept.net/git/site007

With the following command, you create a working copy of the DrupalCONCEPT website repository on your workstation (of course, you'll have to replace the instance details):

    $ git clone https://site007:s3cr3t@pro01.drupalconcept.net/git/site007
  
This command will create a directory `site007` containing a copy of the central repository. This local clone will have a connection to its original so you can easily update your local copy from the central repository and transfer your local changes back to the DrupalCONCEPT platform.

The directory is named `site007` because Git per default uses the last part of the URL path as the clone repository's name. If you'd like to use another name (e.g. `mysite`), simply add it as an command argument:

    $ git clone https://site007:s3cr3t@pro01.drupalconcept.net/git/site007 mysite


## Excluding files from the repository

From the file `.gitignore`, a hidden file in the root directory of the repository, Git reads a list of names and patterns for files that you don't want to have added to the repository. For example, since you don't want put backup files under version control, you can add the pattern `*.bak` in a separate line to `.gitignore`. 

Another important exception are the asset directories like `sites/default/files`. You have to make Git ignore all possible multisite directory names by using a pattern as described below.

We recommend you also exclude `settings.php`, especially if you want to do a staging workflow with separate website instances. On the DrupalCONCEPT hosting platform, you can use a different configuration file for each staging instance, for example `settings.production.php` and `settings.staging.php`. Even if you don't intend to do staging, simply use `settings.production.php`.

So, make sure that `.gitignore` contains at least these lines:

    sites/*/files
    settings.php

Next, you’re going to import a Drupal distribution into your repository.