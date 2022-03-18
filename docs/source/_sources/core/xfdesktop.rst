********************************
xfdesktop - Xfce Desktop Manager
********************************

  * **[[#Minimum Requirements|Minimum Requirements]]**
  * **[[#Debugging Support|Debugging Support]]**
  * **[[#Latest Release|Latest Release]]**
  * **[[#Source Code Repository|Source Code Repository]]**
  * **[[#Reporting Bugs|Reporting Bugs]]**

----

Xfdesktop is a desktop manager for the Xfce Desktop Environment. It handles the following tasks:

* background image / color
* root menu, window list
* minimized app icons
* file icons on the desktop (using Thunar libs)
 
It can bring up an applications menu and a list of all running applications when you click on the desktop with the right or middle mouse button respectively. Settings are available via the [[../:xfce4-settings:|Settings Manager]].

----

General
=======

* **[[usage|Usage]]** -- Overview of the Desktop Manager
* **[[preferences|Preferences]]** -- Configuring the desktop
* **[[command-line|Command-line Options]]** -- Parameters for using ''xfdesktop'' in the command-line
* **[[advanced|Advanced]]** -- Hidden options

----

Minimum Requirements
====================

* intltool 0.31
* GTK+ 3.22.0
* libxfce4util 4.13
* libxfce4ui 4.13
* libwnck 3.14
* libexo 0.11
* xfconf 4.12.1
* garcon 0.6.0 (optional; required for apps menu)
* thunar 1.7.0 (optional; required for file icons)
* tumbler 1.6 (optional; enables thumbnail previews for file icons)
* cairo 1.12


----

Debugging Support
=================

xfdesktop currently supports three different levels of debugging support,
which can be setup using the configure flag ``--enable-debug`` (check the output
of ``configure --help``):


.. csv-table::
   :header: "Argument", "Description"
   
    "yes", "This is the default for Git snapshot builds. It adds all kinds of checks to the code, and is therefore likely to run slower. Use this for development of xfdesktop and locating bugs in xfdesktop."
    "minimum", "This is the default for release builds. **This is the recommended behaviour.**"
    "no", "Disables all sanity checks. Don't use this unless you know exactly what you do. "

----

Latest Release
==============

{{rss>https://archive.xfce.org/feeds/project/xfdesktop 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfdesktop/>`_

----

Source code repository
======================

https://gitlab.xfce.org/xfce/xfdesktop

----

Reporting Bugs
==============

  * **[[:xfce:xfdesktop:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

:start|Back to main Xfce documentation page