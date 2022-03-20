Thunar File Manager
===================

.. Contents::

----

Introduction
------------

//Thunar// is a modern file manager for the Xfce Desktop Environment. //Thunar// has been designed from the ground up to be fast and easy to use. Its user interface is clean and intuitive and does not include any confusing or useless options by default. //Thunar// starts up quickly and navigating through files and folders is fast and responsive.


* **[[the-file-manager-window|The File Manager Window]]** -- working with the Thunar window and modifying the layout
* **[[working-with-files-and-folders|Working with Files and Folders]]** -- basic file handling
* **[[using-removable-media|Using Removable Media]]** -- working with removable devices
* **[[preferences|File Management Preferences]]** -- details of the different file manager preferences
* **[[faq|Frequently Asked Questions]]** -- some random things you probably want to know
* **[[hidden-settings|Advanced Settings]]** -- The xfce4-settings-editor, customize gtk3 css and more possible tweaks
* **[[unix-filesystem| The UNIX filesystem]]** -- understanding the UNIX File System
* **[[send-to|The "Send To" Menu]]** -- how to customize the send to menu

----

Thunar Plugins
--------------

Thunar plugins can be installed as separate, additional packages in order to extend the functionality of Thunar. Most Thunar plugins offer additional options on files in the context menu or via shortcut. The interface which is used by thunar plugins is the `thunarx API <https://git.xfce.org/xfce/thunar/tree/thunarx>`_.

* **[[.:bulk-renamer:|Bulk Renamer]]** -- rename multiple files at once
* **[[custom-actions|Custom Actions]]** -- custom commands associated with common mime-types or extensions
* **[[archive|Archive Plugin (thunar-archive-plugin)]]** -- allows to create and extract archive files
* **[[media-tags|Media Tags Plugin (thunar-media-tags-plugin)]]** -- improved support for ID3 tags
* **[[thunar-shares-plugin|Shares Plugin (thunar-shares-plugin)]]** -- Quickly share folders using Samba without requiring root access
* **[[thunar-volman|Volume Manager (thunar-volman)]]** -- Automatic management of removable devices in Thunar
* **[[thunar-vcs-plugin|VCS Plugin (thunar-vcs-plugin)]]** -- adds Subversion and GIT actions to the context menu

----

Other Thunar Related Packages

  * **[[unix-filesystem#gnome_virtual_file_system|Gnome Virtual File System]]** --  required for trash support, mounting removable media, and [[unix-filesystem#remote_file_systems|remote filesystems]]
  * **[[:xfce:tumbler:start:|Tumbler]]** -- the remote thumbnail service for Thunar

----

Debugging Support
-----------------

Thunar currently supports four different levels of debugging support, which can be setup using the configure flag ``--enable-debug`` (check the output of ``configure --help``):

.. csv-table::
   :header: "Argument", "Description"
    
   "full", "Use this if you want to debug Thunar to locate a bug. The build will most probably be noticably slower. This is also recommended for people that want to develop Thunar stuff."
   "yes", "Adds all kinds of checks to the code, and is therefore likely to run slower. Use this if you want to develop for Thunar (e.g. writing Thunar extensions and such)."
   "minimum", "This is the default for release builds, and presents the recommended behaviour."
   "no", "Disables all sanity checks. Don't use this unless you know exactly what you do."

For some additional build & debug hints, as well check the `Thunar Wiki pages <https://wiki.xfce.org/thunar/dev>`_.

----

Standards compliance
--------------------

Thunar supports the following standards/specifications:

* `XDG Base Directory Specification <https://freedesktop.org/wiki/Specifications/basedir-spec>`_
* `Shared MIME Database Specification <https://freedesktop.org/wiki/Specifications/shared-mime-info-spec>`_
* `X Direct Save (XDS) Protocol for the X Window System <https://freedesktop.org/wiki/Specifications/direct-save>`_
* `Icon Theme Specification <https://freedesktop.org/wiki/Specifications/icon-theme-spec>`_
* `Thumbnail Managing Standard <https://freedesktop.org/wiki/Specifications/thumbnails>`_
* `File URI Specification <https://freedesktop.org/wiki/Specifications/file-uri-spec>`_
* `Desktop Trash Can Specification <https://freedesktop.org/wiki/Specifications/trash-spec>`_

----


Required Packages
-----------------

Thunar depends on the following packages:

* `perl <https://github.com/Perl/perl5>`_
* `GTK+ <https://www.gtk.org>`_
* `GLib <https://wiki.gnome.org/Projects/GLib>`_
* `exo <https://gitlab.xfce.org/xfce/exo>`_
* `libxfce4util <https://gitlab.xfce.org/xfce/libxfce4util>`_
* `libxfce4ui <https://gitlab.xfce.org/xfce/libxfce4ui>`_
* `xfconf <https://gitlab.xfce.org/xfce/xfconf>`_
* `intltool <https://www.freedesktop.org/wiki/Software/intltool/>`_

Thunar can optionally be build with the following packages:

* `D-Bus <https://www.freedesktop.org/wiki/Software/dbus>`_ (strongly suggested, required for inter process communication)
* `xfce-panel <https://gitlab.xfce.org/xfce/xfce4-panel>`_ (required to build the trash panel applet)
* `gudev <https://sourceforge.net/projects/gudev/>`_ (required for thunar-volman)
* `libnotify <https://github.com/GNOME/libnotify>`_ (required for mount notification support)

For concrete information on the minimum required versions, check `configure.ac.in <https://gitlab.xfce.org/xfce/thunar/-/blob/master/configure.ac.in>`_

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/thunar 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/thunar>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/thunar


For additional build, test and debugging tips, see [[https://wiki.xfce.org/thunar/dev/build_and_run|this page]] for more suggestions.

----

Reporting Bugs
--------------

* **[[bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

:start|Back to main Xfce documentation page