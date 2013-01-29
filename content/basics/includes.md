---
title: Includes
---

Fertige Includes zur automatischen Konfigurations
Im Verzeichnis current ist ein Verzeichnis config vorhanden, in dem CMS-spezifische, vorbereitete Dateien liegen, die direkt eingebunden werden können, um bestimmte die Site zu konfigurieren.

Diese können aus einer Konfigurationsdatei des CMS mittels require_once('../config/$CMS/$DATEINAME'); (Pfadangabe ist relativ relativ zum Documentroot) eingebunden werden.

Beispiel settings.php einer Drupal 7 Site

    <?php
    require_once('../config/drupal/settings-d7-db123.php');
    require_once('../config/drupal/settings-d7-site.php');
    ?>

Drupal

settings-d7-dbXXX.php

Drupal 7 Datenbankkonfiguration

settings-d6-dbXXX.php

Drupal 6 Datenbankkonfiguration

settings-d7-site.php

Diverse Settings für Drupal 7 (momentan reverse_proxy)

settings-d6-site.php

Diverse Settings für Drupal 6 (momentan reverse_proxy)
