---
title: "Filesystem structure"
---

# Filesystem structure

## Limited write permissions

Since all web application installations on our infrastructure are cloned from a central Git repository, we have to prevent changes being made directly on the server. There are multiple reasons for that.

Changing a file directly on the server would

1. cause a permanent conflict with the version in the Git repository. This would then cause any further deployment attempts to fail and make tech support necessary. (Some of our early customers know this problem from experience...)
2. destroy version consistency throughout the cluster, because the other cluster nodes would not reflect that local change.

There is no reliable way of feeding local changes back into the central repository. That's why we don't allow Drupal write access to its own distribution files at all. All changes to your Drupal installation have to come via the central Git repository.

Of course, changes to asset files (by way of file uploads or by the ImageCache module, for example) must be possible. On our freistilbox hosting platform, Drupal's write access -- and that's important for you to know -- is limited to its *public and private file system paths* and the *temporary directory*. In a later section, we'll show you how to configure them properly.
