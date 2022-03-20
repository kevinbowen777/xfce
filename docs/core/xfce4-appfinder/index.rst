xfce4-appfinder - Application Finder
====================================

.. Contents::

----

The Application Finder is a program to find and launch installed applications on your system, and quickly execute commands. It does this by searching your file system for ``.desktop`` files, and displays a categorized list of all the GUI applications on your system.

.. Tip:: You can use the Application Finder to quickly add [[:xfce:xfce4-panel:launcher|launchers]] to your [[:xfce:xfce4-panel:|panel]] - simply drag an item onto your desired panel and it will automatically create a launcher for that application.</note>

----

General
-------

* **[[usage|Usage]]** -- Overview of the Application Finder
* **[[preferences|Preferences]]** -- Configure the behaviour of the application and create custom actions
* **[[examples|Custom Action Examples]]** -- Examples for custom actions

----

Debugging Support
-----------------

xfce4-appfinder currently supports three different levels of debugging support,
which can be setup using the configure flag ``--enable-debug`` (check the output of ``configure --help``):

.. csv-table::
   :header: "Argument", "Description"
    
    "yes", "This is the default for Git snapshot builds. It adds all kinds of checks to the code, and is therefore likely to run slower. Use this for development of xfce4-appfinder and locating bugs in xfce4-appfinder."
	"minimum", "This is the default for release builds. **This is the recommended behaviour.**"
	"no", "Disables all sanity checks. Don't use this unless you know exactly what you do."

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/xfce4-appfinder 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfce4-appfinder/>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/xfce4-appfinder

----

Reporting Bugs
--------------

* **[[bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

start|Back to main Xfce documentation page