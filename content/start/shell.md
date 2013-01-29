---
title: Shell access
---

cXXs.freistilbox.net ist ein eigener Shellserver. Jede Site hat dort einen eigenen User.

Im Verzeichnis current findest du einen zu den Webfrontends identischen Checkout, sowie Links zu private Verzeichnissen und den präparierten Konfigurationsincludes.
Das Drupal selbst befindet sich also in current/docroot.

Die gleiche Verbindung (s123@cXXs.freistilbox.net) wird auch für SFTP verwendet. Public files liegen in current/docroot/sites/default/files bzw. dort sie im Boxfile unter shared_folders definiert wurden.

ssh s123@cXXs.freistilbox.net


    <?php
    $aliases['s123'] = array(
      'uri' => 's123.cXX.freistilbox.net',
      'root' => '/srv/www/freistilbox/clients/c10789/s123/current/docroot',
      'remote-host' => 'cXXs.freistilbox.net',
      'remote-user' => 's123',
    );
