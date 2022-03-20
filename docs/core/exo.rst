=========================
Exo - Helper Applications
=========================

.. Contents::

----

Exo is an extension library used in the Xfce desktop, originally developed by `os-cillation <https://www.os-cillation.de/en/opensourceprojekte/libexo/>`_. It has some helper applications that are used throughout the entire Xfce desktop to manage preferred applications and edit ``.desktop`` files.

exo is targeted at application development and is considered ready for production use. You no longer need to define the EXO_API_SUBJECT_TO_CHANGE preprocessor symbol.

----

Applications
------------

* **[[desktop-item-edit|Desktop Item Editor (exo-desktop-item-edit)]]** -- Editor for .desktop files

* **[[preferred-applications|Preferred Applications (exo-preferred-applications)]]** -- Select the default applications to be used for various services, i.e. the web browser that should be used to open hyperlinks

----

Required Packages
-----------------

* `GIO <https://docs.gtk.org/gio/>`_
* `GLib <https://wiki.gnome.org/Projects/GLib>`_
* `GTK+ <https://www.gtk.org>`_
* gthread
* `libxfce4ui <https://gitlab.xfce.org/xfce/libxfce4ui>`_
* `libxfce4util <https://gitlab.xfce.org/xfce/libxfce4util>`_
* gio-unix

----

Debugging Support
-----------------

libexo currently supports four different levels of debugging support, which
can be setup using the configure flag ``-enable-debug`` (check the output of
``configure --help``):

.. code-block:: rst

    `full'    This is the strongest option. Deprecation and some coding style
              checks are made and will cause the build to fail for any errors
              or warnings.

    `yes'     This is the default for Git snapshot builds. It adds all kinds
              of checks to the code, and is therefore likely to run slower.
              Use this for development of libexo and locating bugs in libexo.

    `minimum' This is the default for release builds. This is the recommended
              behavior.

    `no'      Disables all sanity checks. Don't use this unless you know
              exactly what you are doing.

Back to Top

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/exo 1 date description 2h}}

`Previous Versions <https://archive.xfce.org/src/xfce/exo>`_

Back to Top

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/exo

----

Reporting Bugs
--------------

* **[[bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs


Back to Top

----

:start|Back to main Xfce documentation page