---
title: "The Boxfile"
---

# The Boxfile

The Boxfile is a file of the same name that is stored in the root directory of a single web application's repository. It defines attributes that control the deployment process.

The format of the Boxfile is YAML.

Example:

    version: 1.0
    shared_folders:
      - sites/default/files
    env_specific_files:
      .htaccess:
        production: .htaccess.production
        test: .htaccess.test
      .htpasswd:
        production: .htpasswd.production
        test: .htpasswd.test
      sites/default/settings.php:
        production: settings.production.php
        test: settings.test.php


## Shared folders

Shared folders are part of the application code space but need to be shared between all application servers of a cluster since they are writable by the web application.

Public shared folders are defined in a shared_folders collection as a list of paths, relative to the application's document root:

    shared_folders:
      - sites/default/files
      - sites/www.example.com/files

Private shared folders can be directly created via SFTP/SSH in the docroot/private folder and are reachable via ../private relative to the application's document root.


## Environment-specific files

Environment-specific files are alternative configuration files that are used only in a specific staging environment. For example, this could be used for providing a variation of the application's database credentials for each development stage.

    env_specific_files:
      .htaccess:
        production: .htaccess.production
        test: .htaccess.test
      .htpasswd:
        production: .htpasswd.production
        test: .htpasswd.test
      sites/default/settings.php:
        production: settings.production.php
        test: settings.test.php
