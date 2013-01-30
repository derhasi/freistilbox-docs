---
title: "The Basics of freistilbox"
---

# The basics of the freistilbox hosting platform

## Distributed Architecture

TODO: Write introductory paragraph about performance, availability, scalability.

**Boxes:** On the freistilbox hosting platform, your web application is installed on one or more application servers ("boxes"), together called the "freistilbox cluster". 

**SSL offloader:** TODO: Write description

**Load balancer:** TODO: Write description

**Caches:** TODO: Write description

**Shell box:** To give you manual access to your website's asset files and the opportunity to do a remote login and execute commands directly in the freistilbox environment, another box is added to your freistilbox cluster especially for these purposes. It doesn't respond to page requests, so jobs running on this box are not likely to interfere with the delivery of your website content.

**Backend:** Your web application usually uses several backend services, for example MySQL, shared storage or Apache Solr. These services run on dedicated clusters that are usually shared by a number of customers.




## Central deployment

Distributing your web application code on the multiple nodes of a freistilbox cluster will work only if it is installed completely identical on all cluster nodes at all times. Inconsistencies, for example in the form of different cde revisions, will result in website behaviour that would at least confuse your visitors or, in the worst case, break your website. 

To avoid these problems, we provide a centralized deployment process. You need to upload your changes only once; our infrastructure then takes care of distributing them to all affected boxes within seconds.


## Version control with Git

Updating distributed services from a central code base is the ideal task for modern version control systems. We chose Git for that purpose.

Every freistilbox website instance has its own central Git repository that stores its Drupal installation. From this central repository, all the webservers responsible for delivering your site update their local Drupal environment after every change you upload. Technically speaking, they clone the central repository.


## Limited write permissions

Since all web application installations on our infrastructure are cloned from a central Git repository, we have to prevent changes being made directly on the server. There are multiple reasons for that.

Changing a file directly on the server would

1. cause a permanent conflict with the version in the Git repository. This would then cause any further deployment attempts to fail and make tech support necessary. (Some of our early customers know this problem from experience...)
2. destroy version consistency throughout the cluster, because the other cluster nodes would not reflect that local change.

There is no reliable way of feeding local changes back into the central repository. That's why we don't allow Drupal write access to its own distribution files at all. All changes to your Drupal installation have to come via the central Git repository.

Of course, changes to asset files (by way of file uploads or by the ImageCache module, for example) must be possible. On our DrupalCONCEPT hosting platform, Drupal's write access -- and that's important for you to know -- is limited to its *public and private file system paths* and the *temporary directory*. In a later section, we'll show you how to configure them properly.




* [The website repository](repository/)
* [The Boxfile](boxfile/)
* [Ready-made configuration files](includes/)
