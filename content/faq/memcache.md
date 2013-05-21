---
Title: "How do I configure Memcache?"
---

We have already prepared configuration files with all important details
necessary to use Memcache. Their path schema is as follows relative to
`docroot`:

`../config/drupal/settings-DRUPALVERSION-memcache.php`

Since all the necessary details are already pre-configured in these
files, you simply include the appropriate file in your
`settings.production.php` and set the right caching module for your Drupal
version.

### Configuration example for Drupal 7:

    require_once('../config/drupal/settings-d7-memcache.php');  
    $conf['cache_backends'][] = 'sites/all/modules/contrib/memcache/memcache.inc';

### Configuration example for Drupal 6:

    require_once('../config/drupal/settings-d6-memcache.php');  
    $conf['cache_inc'] = './sites/all/modules/contrib/memcache/memcache.inc';

#### Info

Please note to set the correct path to the `memcache.inc` file!
