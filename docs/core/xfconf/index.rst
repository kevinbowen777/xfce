xfconf - Configuration Storage System
=====================================

.. Contents::

----

Introduction
------------

Xfconf is a hierarchical (tree-like) configuration system where the immediate child nodes of the root are called ``channels``.  All settings beneath the channel nodes are called ``properties.``

Valid channel and property names are composed of the ASCII US-English uppercase characters A-Z, lowercase characters a-z, numerals 0-9, the dash (-), and underscore (_).  No other characters are allowed for channel names.  The less than (<) and greater than (>) characters (aka ``angle brackets``) are also allowed in property names, but not in channel names.

Property names are referenced by their ``full path`` underneath their channel, for example: ``/main/history-window/last-accessed``.  Of course, when querying a particular property, the channel must be specified separately as well.

Both channel and property names are case-insensitive.  For example, the following four all refer to the same property:

* Channel: ExampleApp, property: /main/history-window/last-accessed
* Channel: EXAMPLEAPP, property: /main/history-window/last-accessed
* Channel: ExampleApp, property: /Main/History-Window/Last-Accessed
* Channel: exampleapp, property: /MAIN/history-window/last-accessed

----

Accessing Configuration Data
-----------------------------

Settings stored in Xfconf can be accessed in numerous ways:

* From within applications of Settings Manager. Most of the time, settings stored in Xfconf and configuration options presented in the GUI are tightly coupled. It means that any action of the GUI settings is automatically and immediately propagated to the configuration system and vice-versa. See also: [[xfce:xfce4-settings:xfsettingsd|Settings Daemon]].
* From Command Line Interface (CLI) using [[:xfce:xfconf:xfconf-query:|xfconf-query]].
* From GUI. Settings, which are not exposed in configuration dialogs, can be browsed and manipulated using [[xfce:xfce4-settings:editor|Settings Editor]].
* If everything else fails, settings can be edited manually. Xfconf stores all its data in [[xml-file-format|XML files]], which can be edited when Xfconf is not running. Be very careful when using this option, as it is easy to make the file unparseable or inconsistent.

----

Kiosk Mode
----------

System administrators can lock certain values or entire channels to prevent users from changing them.  In this case, the administrator may provide default values that will be used regardless of what may appear in a user-writable configuration file.  If the sysadmin does not wish to provide values, but only wants to lock a channel/property, the application's default fallback value will be used instead.
   
Locking a channel or property is as simple as creating a configuration file and setting either (and only either) the ``locked`` or ``unlocked`` attribute on <channel> or <property> elements that should be restricted.  This configuration file should be placed in a system location that is read by the daemon (see ``File locations`` above).
   
Both the "locked" and ``unlocked`` attributes take a semicolon-separated list of system user and group names.  User names should be entered as-is, and group names should be entered with an ``@`` symbol prepended to the group name.
   
The "locked" attribute specifies users and groups who may not modify the property.  The ``unlocked`` attribute specifies users and groups who may modify the property, with other users locked out.  Only one of the two attributes may be specified for a particular channel or property.  If both are present, the ``unlocked`` attribute is used, and the ``locked`` attribute is ignored.
   
Note that <channel> locking locks all properties under that channel, but <property> locking locks only the property with the ``locked`` or ``unlocked`` attribute; none of the sub-properties are locked unless they also contain a ``locked`` or ``unlocked`` attribute.

See [[:xfce:xfce4-session:advanced#kiosk_mode|Xfce-Session Kiosk Mode]] for specific parameter used in configuring kiosk mode.

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/xfconf 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfconf/>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/xfconf

----

Reporting Bugs
--------------

* **[[:xfce:xfconf:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

[[ :xfce:xfce4-settings:start:|Return to main xfce4-settings page]]

[[:start|Back to main Xfce documentation page]]