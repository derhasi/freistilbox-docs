---
title: "Frequently asked questions"
---

# Q: Is there a backup of my website's data? 

We do nightly (relative to UTC) backups of all your website data:

* Application repository
* Database
* Asset files

We keep backups for 3 (three) days.

The application repository can only be restored as whole, mostly after data corruption. Since you've probably got a clone of the repository that's at least as recent as our backup, we can alternatively wipe the repository so you can push your data again.

Databases are stored as SQL dumps. If you need to restore a database backup, we make the dump available to you in your website's `backup` directory.

Asset files can be restored by our operations team directly to their original location.
