---
title: Pre-configured settings snippets
---

# Pre-configured settings snippets

In the `current` directory, you'll find a subdirectory named `config` with CMS-specific configuration snippets. You can include these snippets into your web application settings to have important services configured automatically.

In PHP, you can include such a snippet simply with the statement `require_once('../config/$CMS/$CONF');` (this path is relative to your `docroot`).

Example: `settings.php` for a Drupal 7 site

    <?php
    require_once('../config/drupal/settings-d7-db123.php');
    require_once('../config/drupal/settings-d7-site.php');
    ?>

## Drupal configuration snippets

* Database configuration: `settings-d7-dbXXX.php` (replace "dbXXX" with the database name mentioned in the installation details of your site instance)
* Miscellaneous settings (e.g. `reverse_proxy`): `settings-d7-site.php`

For Drupal 6 sites, simply replace "d7" with "d6".
