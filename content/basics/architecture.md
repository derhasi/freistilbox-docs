---
title: "Architecture"
---

# Distributed Architecture

TODO: Write introductory paragraph about performance, availability, scalability.

**Boxes:** On the freistilbox hosting platform, your web application is installed on one or more application servers ("boxes"), together called the "freistilbox cluster". 

**SSL offloader:** TODO: Write description

**Load balancer:** TODO: Write description

**Caches:** TODO: Write description

**Shell box:** To give you manual access to your website's asset files and the opportunity to do a remote login and execute commands directly in the freistilbox environment, another box is added to your freistilbox cluster especially for these purposes.

**Backend:** Your web application will probably use several backend services, for example MySQL, shared storage or Apache Solr. These services run on dedicated clusters that are usually shared by a limited number of customers.

