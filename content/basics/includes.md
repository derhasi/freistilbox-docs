---
title: Includes
---

TODO: Translate to English

# Fertige Includes zur automatischen Konfiguration

Das Verzeichnis `current` enthält ein Unterverzeichnis `config`, in dem CMS-spezifische, vorbereitete Dateien liegen, die direkt eingebunden werden können, um bestimmte Aspekte der Webapplikation zu konfigurieren.

Diese können aus einer Konfigurationsdatei des CMS mittels `require_once('../config/$CMS/$DATEINAME');` (Pfadangabe ist relativ relativ zum Document Root) eingebunden werden.

Beispiel: `settings.php` einer Drupal-7-Site

    <?php
    require_once('../config/drupal/settings-d7-db123.php');
    require_once('../config/drupal/settings-d7-site.php');
    ?>

## Drupal

* Drupal 7 Datenbankkonfiguration: `settings-d7-dbXXX.php`
* Drupal 6 Datenbankkonfiguration: `settings-d6-dbXXX.php`
* Diverse Settings für Drupal 7 (momentan reverse_proxy): `settings-d7-site.php`
* Diverse Settings für Drupal 6 (momentan reverse_proxy): `settings-d6-site.php`
