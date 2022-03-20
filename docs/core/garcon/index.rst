garcon - menu library
=====================

.. Contents::

----

**Garcon** is an implementation of the `freedesktop.org compliant menu <https://specifications.freedesktop.org/menu-spec/latest/>`_ specification. It is based on GLib/GIO and aims at covering the entire specification except for legacy menus. It was started as a complete rewrite of the former Xfce menu library called libxfce4menu, which, in contrast to garcon,
was lacking menu merging features essential for loading menus modified with menu editors.

----

Introduction
------------

Garcon covers almost every part of the menu specification except for
legacy menus and a few XML attributes. In contrast to
libxfce4menu, it can also load menus modified with menu editors such
as Alacarte as menu merging is now supported. The only crucial
feature still missing is monitoring menus and menu items for changes.
This is something that will be worked on for the next release.

The garcon API will most likely not be frozen until its 1.0.0 release (It is currently at version 0.7.1)!

----

Required Packages
-----------------

* `GIO <https://docs.gtk.org/gio/>`_
* `GLib <https://wiki.gnome.org/Projects/GLib>`_
* gobject
* gthread
* `GTK+ <https://www.gtk.org>`_
* `libxfce4ui <https://gitlab.xfce.org/xfce/libxfce4ui>`_
* `libxfce4util <https://gitlab.xfce.org/xfce/libxfce4util>`_

----

Debugging Support
-----------------

garcon currently supports three different levels of debugging support,
which can be setup using the configure flag ``--enable-debug`` (check the output
of ``configure --help``):

.. csv-table::
   :header: "Argument", "Description"
    
   "yes" ,"This is the default for Git snapshot builds. It adds all kinds of checks to the code, and is therefore likely to run slower. Use this for development of garcon and locating bugs in garcon."
   "minimum", "This is the default for release builds. **This is the recommended behaviour.**"
   "no", "Disables all sanity checks. Don't use this unless you know exactly what you do."

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/garcon 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/garcon>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/garcon

----

Reporting Bugs
--------------

* **[[:xfce:garcon:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs


----

:start|Back to main Xfce documentation page