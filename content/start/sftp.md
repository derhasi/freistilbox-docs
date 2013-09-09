---
title: "Access to asset files"
---

# Access to asset files

We have separated the files with application code from the asset files that are user-generated. This has several reasons:

1. While it's useful to have all your software components (core application, 3rd party add-ons, themes etc.) under version control, it makes no sense to do so for asset files. Many of these files will be created and modified by your application on the web frontend.
2. For performance reasons, application code and asset files are stored in different places on the freistilbox hosting platform.

For these reasons, you maintain asset files not via Git but by accessing them directly using the secure SFTP protocol.

In your SFTP client of choice (more on that below) you then enter the hostname of the website instance (for example `pro1.freistilbox.net`) and use the website instance ID as user name (for example `site007`).


## SFTP client software

File transfer software capable of SFTP is available for every common operating system:

* *Windows:* [WinSCP][winscp], [FileZilla][filezilla]
* *OS X:* [Cyberduck][cyberduck], [Transmit][transmit]
* *Linux:* [FileZilla][filezilla]

[winscp]: http://winscp.net/
[filezilla]: http://sourceforge.net/projects/filezilla/
[cyberduck]: http://cyberduck.ch/
[transmit]: http://panic.com/transmit/


## SFTP access keys

SSH, and in extension its file transfer protocol SFTP, uses public key authentication to create secure data transfer connections. This makes it necessary that you generate a pair of keys, stored separately in a private key file (`id_rsa` or `id_dsa`) and a public key file (`id_rsa.pub` or `id_dsa.pub`). Please refer to your SFTP client's manual how do to execute this.

Please keep your private key file, as the name implies, private. It identifies and authorizes you and should only be accessed and used by yourself.

To give you access to our servers, we need to install your *public key*. We ask you to send your public key to our [technical support](mailto:support@freistil.it), together with the site ID of the respective website instance. Please make sure that the public key is in the OpenSSH format (it should look similar to `ssh-rsa AAAAB3NzaC1yc2E... some comment`).
