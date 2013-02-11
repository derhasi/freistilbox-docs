---
title: Configuring Drupal
---

# Ready-made Drupal Configuration

For the reasons explained previously, Drupal doesn't have the permissions to modify files in its installation. This write restriction also pertains to the `settings.php` file. Because Drupal can't write to this file during the initial installation process, you have to maintain the main settings file manually. As already mentioned, we recommend you use stage-specific file names; `settings.production.php` is the default.

To make configuring your Drupal installation as simple as possible, we provide pre-configured settings files. By using the PHP function `require()`, you can easily include them in your main settings file.


## Configuring the website

For each website instance, we provide a configuration file with basic settings, for example the correct reverse proxy settings:

    ../config/drupal/settings-DRUPALVERSION-site.php

Replace `DRUPALVERSION` with "d6" or "d7".

Here's an example that includes the Drupal 6 site configuration for client `client1`, website instance `site007`:

    require '../config/drupal/settings-d6-site.php';


## Configuring the database

For each database of your website instance, we provide a separate configuration file that contains all necessary credentials to access the database from Drupal. The directory path of these configuration files follows this schema:

    ../config/drupal/settings-DRUPALVERSION-DBID.php
    
Replace `DRUPALVERSION` with "d6" or "d7".

Here's an example that includes the Drupal 6 database configuration for the database `db007`:

    require '../config/drupal/settings-d6-db007.php';

## Creating a site alias for drush

With access to the [shell host](/start/shell/) you get access to using
site aliases with drush as well.

This is a minimal working `aliases.drushrc.php`:

    <?php
    $aliases['s123'] = array(
      'uri' => 's123.cXX.freistilbox.net',
      'root' => '/srv/www/freistilbox/clients/c98765/s123/current/docroot',
      'remote-host' => 'cXXs.freistilbox.net',
      'remote-user' => 's123',
    );

