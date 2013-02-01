---
title: Deployment
---

# Central deployment

Distributing your web application code on the multiple nodes of a freistilbox cluster will work only if it is installed completely identical on all cluster nodes at all times. Inconsistencies, for example in the form of different code revisions, will result in website behaviour that would at least confuse your visitors or, in the worst case, break your website. 

To avoid these problems, we provide a centralized deployment process. You need to upload your changes only once; our infrastructure then takes care of distributing them to all affected boxes within seconds.


## Version control with Git

Updating distributed services from a central code base is the ideal task for modern version control systems. We chose Git for that purpose.

Every freistilbox website instance has its own central Git repository that stores its Drupal installation. From this central repository, all the webservers responsible for delivering your site update their local Drupal environment after every change you upload. Technically speaking, they clone the central repository.


## Aufbau des Git Repository

TODO: Translate to English

Die Webanwendung muss in einem Verzeichnis docroot liegen.
Dies ist dann auch das Documentroot für den Webserver.

.gitignore kann dementsprechend angepasst werden.

Boxfile ist eine Konfigurationsdatei mit der Entwickler Parameter der Hostingumgebungen (vorerst: Shared Folder und automatische Verlinkungen nach Environment) steuern können.
