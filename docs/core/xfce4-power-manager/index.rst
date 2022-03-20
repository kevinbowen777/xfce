xfce4-power-manager - Power Manager
===================================

.. Contents::

----

Introduction
------------

Xfce4 Power Manager manages the power sources of the computer and connected devices (wireless mice, keyboards, media players etc.). It also allows users to control the display backlight brightness and set power-saving modes for displays and monitors.\\
In addition, xfce4-power-manager provides a set of freedesktop-compliant DBus interfaces to inform other applications about the current power level so that they can adjust their power consumption, and it provides the inhibit interface which allows applications to prevent automatic sleep actions via the power manager; as an example, the operating system’s package manager should make use of this interface while it is performing update operations.

----

Additional Information
----------------------

  * **[[:xfce:xfce4-power-manager:getting-started|Getting Started]]** -- Starting the power manager and some command-line options.

  * **[[:xfce:xfce4-power-manager:preferences|Preferences]]** -- Customizing the settings of the power manager.

  * **[[:xfce:xfce4-power-manager:faq|Frequently Asked Questions]]** -- Some random things you probably want to know.

  * **[[:xfce:xfce4-power-manager:panel-plugin|Power Manager Panel Plugin]]** -- Display your battery's load status, connected devices and control your display backlight brightness.

----

Required packages
-----------------

Xfce Power Manager depends on the following packages:

* Gtk 3.14 or above.
* Glib 2.42 or above.
* DBus 1.1 or above.
* libxfce4ui 4.12.0 or above.
* libxfce4util 4.12.0 or above
* libnotify 0.4.1 or above.
* xfconf 4.12.0 or above.
* libxfce4panel 4.12.0 or above (optional, for the Xfce panel plugin).
* XRandR 1.2.0 or above.
* DPMS X11 extension (DPMS support, required).
* UPower 0.99.0 or above.
* Polkit 0.91 or above (optional but recommended).
* Consolekit (optional but recommended).
* LoginD/SystemD (optional).
* Pm-utils (for suspend & hibernate on Linux).

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/xfce4-power-manager 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfce4-power-manager/>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/xfce4-power-manager

----

Reporting Bugs
--------------

  * **[[bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

start|Back to main Xfce documentation page