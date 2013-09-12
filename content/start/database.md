---
title: Database
---

# Database

We provide pre-populated configuration snippets that you can simply include in your application configuration.

## Drupal

To include a configuration snippet, you just need a single line:

    require_once('../config/drupal/settings-d7-dbXXX.php');

Obviously, you need to replace "dbXXX" with the database ID we gave you in the installation message for your application instance. If your application uses Drupal 6, replace "d7" with "d6".

<span class="label label-warning">Warning</span> Make sure to add this line at the end of your `settings.XYZ.php` so its settings can't be overridden by other configuration entries.

If you'd like to see the contents of the configuration snippet, you can find it on the [shell host](/start/shell/) under `current/config/drupal/`.
