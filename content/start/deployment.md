---
title: "Deploying your web application"
---

To deploy your Drupal installation to our freistilbox hosting platform, you transfer all the changes you've made to the repository to the central repository. You do this by using a simple command:

    $ git push origin master

By doing a "push", you transfer all changes you've made since you've cloned or updated your local repository from the central repository back to it.

A sophisticated deployment mechanism now takes care that all Drupal frontend servers start to deliver this new version of your Drupal installation. It also chooses the correct configuration file which most of the times will be `settings.production.php`.


<p><i class="icon-warning-sign"> </i> Because Git is a distributed version control system, you can clone as many repositories from the central one as you like -- for example in a development team. You need to be careful, though, when you push changes from different repositories. Since these repositories tend to diverge in their commit history, pushing changes from different source repositories can lead to conflicts when those changes need to be merged together on the freistilbox infrastructure. Those conflicts then block all further updates and can only be resolved by our tech support. That's why we recommend using a *single, central repository* to first consolidate all changes from the different developer repositories and then push those to the hosting platform.</p>


## Finish the installation process

Since the database connection is already configured, all you need to do now is run the Drupal installation script by visiting the following URL in your browser:

    http://SITEID.HOSTNAME/install.php

For example:

    http://site007.pro01.freistilbox.net/install.php

Drupal will then do all remaining installation steps like creating its database tables.


## And we're running!

You can now test your website in your browser by visiting its internal test URL which has the following format:

    http://SITEID.HOSTNAME/

For example:

    http://site007.pro01.freistilbox.net/

----

Now it's time for some fine-tuning!