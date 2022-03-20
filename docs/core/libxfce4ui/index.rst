libxfce4ui - widget sharing library
===================================

.. Contents::

----

The libxfce4ui library is used to share commonly used Xfce widgets among the Xfce applications.

----

Required packages
-----------------

Libxfce4ui depends on the following packages:

* GTK+ 3.18.0 or above
* GLib 2.42.0 or above
* Libxfce4util 4.12.0 or above

----

Debugging Support
-----------------

Libxfce4ui currently supports four different levels of debugging support, which
can be setup using the configure flag ``--enable-debug`` (check the output of
``configure --help``):

.. code-block:: rst

    `full'	Use this if you want to debug libxfce4ui to locate a bug. The
  		build will most probably be noticably slower. This is also
		recommended for people that want to develop Xfce applications.

    `yes'		This is the default for SVN snapshot builds. It adds all
  		kinds of checks to the code, and is therefore likely to run
		slower. Use this if you want to develop for Xfce.

    `minimum'	This is the default for release builds, and presents the
  		recommended behaviour.

    `no'		Disables all sanity checks. Don't use this unless you know
  		exactly what you do.

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/libxfce4ui 1 date description 2h}}

`Releases <https://archive.xfce.org/src/xfce/libxfce4ui>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/libxfce4ui

----

Reporting Bugs
--------------

* **[[:xfce:libxfce4ui:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

:start|Back to main Xfce documentation page