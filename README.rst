TKLDev - TurnKey Development Toolchain and Build System
=======================================================

TKLDev is the mother of all TurnKey apps. It's used to give birth to all
TurnKey apps, including new versions of `itself`_. It's designed to make
simple things simple, and hard things possible. It's a self-contained
build system that can be used to rapidly prototype and repeatably build
any generic Debian-based Linux distribution or TurnKey GNU/Linux system
`from source`_.

To get started read the `documentation`_. Read the `blog post`_
announcing TKLDev for the background story. 

This version was customized by CLVsol to include:

An easy to use file server that combines Windows-compatible network file
sharing with an advanced web based file manager and includes support for
SMB, SFTP and rsync file transfer protocols. The server is configured to
allow server users to manage files in private or public storage. Based
on Samba and AjaXplorer.

This appliance includes all the standard features in `TurnKey Core`_,
and on top of that:

- SSL support out of the box.
- Webmin module for configuring Samba.
- Includes popular compression support (zip, rar, bz2).
- Includes flip to convert text file endings between UNIX and DOS
  formats.
- File server (`Samba`_) configurations:
   
   - Preconfigured wordgroup: WORKGROUP
   - Preconfigured netbios name: FILESERVER
   - Configured Samba and UNIX users/groups synchronization (CLI and
     Webmin).
   - Configured root as administrative samba user.
   - Configured shares:
      
      - Users home directory.
      - Public storage.
      - CD-ROM with automount and umount hooks (/media/cdrom).

- Access your files securely from anywhere via `AjaXplorer`_:
   
   - Rich web GUI, with online previews of major formats and drag-n-drop
     support.
   - Dedicated `iOS`_ and `Android`_ apps for on-the-go access.
   - Pre-configured multi-authentication (Local and Samba).
   - Pre-configured repositories (storage, user home directories).

- Default storage: */srv/storage*
- Accessing file server via samba on the command line::

    smbclient //1.0.0.61/storage -Uroot
    mount -t cifs //1.0.0.61/storage /mnt -o username=root,password=PASSWORD

- Includes a fast copy-on-write build toolchain based on 
  GNU make, `fab`_, and `deck`_.
- Turnkey development directory structure with preconfigured CDPATH.
- Integrated caching proxy for fast and iterative development.
- Full usage and development `documentation`_.

Example build sources
---------------------

- `TurnKey GNU/Linux apps <https://github.com/turnkeylinux-apps>`_
- `Community developed distributions <https://github.com/turnkeylinux/tracker/issues?labels=new-appliance>`_

Credentials *(passwords set at first boot)*
-------------------------------------------

-  Webmin, Webshell, SSH, Samba: username **root**
-  Web based file manager (AjaXplorer):
   
   - username **admin** (Local)
   - username **root** (Samba)

.. _itself: https://github.com/turnkeylinux-apps/tkldev
.. _blog post: http://www.turnkeylinux.org/blog/introducing-tkldev
.. _fab: https://github.com/turnkeylinux/fab
.. _deck: https://github.com/turnkeylinux/deck
.. _from source: https://github.com/turnkeylinux-apps/
.. _TurnKey Core: http://www.turnkeylinux.org/core
.. _documentation: https://github.com/turnkeylinux-apps/tkldev/tree/master/docs
.. _Samba: http://www.samba.org/samba/what_is_samba.html
.. _AjaXplorer: http://ajaxplorer.info
.. _iOS: http://ajaxplorer.info/extensions/ios-client/
.. _Android: http://ajaxplorer.info/extensions/android/
