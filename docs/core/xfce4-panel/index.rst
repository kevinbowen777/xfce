xfce4-panel - Xfce Panel
========================

.. Contents::

----

The Xfce Panel is part of the Xfce Desktop Environment and features application launchers, panel menus, a workspace switcher and more. Many aspects of the panel can be configured through the GUI, but also by GTK+ style properties and hidden Xfconf settings. 

----

General
-------

  * **[[getting-started|Getting Started]]** -- Starting the Xfce Panel for the first time
  * **[[add-new-items|Add New Items]]** -- Add new plugins to the Xfce Panel
  * **[[preferences|Preferences]]** -- Configure the Xfce Panel
  * **[[https://wiki.xfce.org/howto:customize-menu|Customize the Xfce menu]]** -- Customize menu entries
  * **[[theming|Theming]]** -- Styling the Xfce Panel

----

Internal Plugins
----------------

  * **[[actions|Action Buttons]]** -- Adds system action buttons to the panel
  * **[[applicationsmenu|Applications Menu]]** -- Adds a menu containing categories of installed applications
  * **[[clock|Clock]]** -- What time is it? -- a clock plugin for the panel.
  * **[[directorymenu|Directory Menu]]** -- Show a directory tree in a menu
  * **[[launcher|Launcher]]** -- Program launcher with optional menu
  * **[[systray|Notification Area]]** -- Area where notification icons appear
  * **[[separator|Separator]]** -- Adds a separator or space between panel plugins
  * **[[showdesktop|Show Desktop]]** -- Hide all windows and show the desktop
  * **[[tasklist|Window Buttons]]** -- Switch between open windows using buttons
  * **[[windowmenu|Window Menu]]** -- Switch between open windows using a menu
  * **[[pager|Workspace Switcher]]** -- Switch between virtual desktops


----

External Plugins
----------------

  * **[[:panel-plugins:xfce4-battery-plugin:start|Battery]]** -- A battery monitor panel plugin for Xfce4 compatible with APM and ACPI, for Linux and *BSD. 
  * **[[:panel-plugins:xfce4-calculator-plugin:start|Calculator]]** -- a calculator plugin for the Xfce4 panel.
  * **[[:panel-plugins:xfce4-clipman-plugin:start|Clipman]]** -- A clipboard manager for Xfce
  * **[[:panel-plugins:xfce4-cpufreq-plugin:start|Cpufreq]]** -- shows information about the CPU governor and frequencies supported and used by your system.
  * **[[:panel-plugins:xfce4-cpugraph-plugin:start|Cpugraph]]** -- offers multiple display modes (LED, gradient, fire, etc…) to show the current CPU load of the system.
  * **[[:panel-plugins:xfce4-datetime-plugin:start|Datetime]]** -- shows the date and time in the panel, and a calendar appears when you left-click on it.
  * **[[:panel-plugins:xfce4-diskperf-plugin:start|Diskperf]]** -- displays instant disk/partition performance (bytes transferred per second).
  * **[[:panel-plugins:xfce4-docklike-plugin:start|Docklike]]** -- A modern, minimalist taskbar for Xfce.
  * **[[:panel-plugins:xfce4-embed-plugin:start|Embed]]** -- Embed arbitrary application windows into the panel.
  * **[[:panel-plugins:xfce4-eyes-plugin:start|Eyes]]** -- Eyes that spy on you. 
  * **[[:panel-plugins:xfce4-fsguard-plugin:start|Fsguard]]** -- checks the chosen mountpoint for free disk space. 
  * **[[:panel-plugins:xfce4-genmon-plugin:start|Genmon]]** -- spawns the indicated script/program, captures its output (stdout) and displays the resulting string into the panel.
  * **[[:panel-plugins:xfce4-indicator-plugin:start|Indicator]]** -- small plugin written by Mark Trompell to display information from various applications consistently.
  * **[[:panel-plugins:xfce4-mailwatch-plugin:start|Mailwatch]]** -- multi-threaded, multi-mailbox, multi-protocol plugin for checking mails periodically. 
  * **[[:panel-plugins:xfce4-mount-plugin:start|Mount]]** -- a mount/umount utility for the panel. 
  * **[[:panel-plugins:xfce4-mpc-plugin:start|Mpc]]** -- client plugin for MPD, the Music Player Daemon
  * **[[:panel-plugins:xfce4-netload-plugin:start|Netload]]** -- displays the current load of the network interfaces, currently works on Linux, *BSD, Sun Solaris, HP_UX and MacOS X. 
  * **[[:panel-plugins:xfce4-notes-plugin:start|Notes]]** -- provides sticky notes for your desktop.
  * **[[:panel-plugins:xfce4-places-plugin:start|Places]]** -- a menu with quick access to folders, documents, and removable media.
  * **[[:panel-plugins:xfce4-pulseaudio-plugin:start|PulseAudio Plugin]]** -- Adjust audio volume and control media players on the Xfce desktop
  * **[[:panel-plugins:xfce4-sample-plugin:start|Sample]]** -- Sample plugin developers can use as a base for new panel-plugins	
  * **[[:panel-plugins:xfce4-sensors-plugin:start|Sensors]]** -- a hardware sensors plugin for the panel.
  * **[[:panel-plugins:xfce4-smartbookmark-plugin:start|Smartbookmark]]** -- allows you to do a search directly on Internet on sites like google or debian bugzilla. 
  * **[[:panel-plugins:xfce4-statusnotifier-plugin:start|Statusnotifier]]** -- provides a panel area for status notifier items (application indicators).
  * **[[:panel-plugins:xfce4-stopwatch-plugin:start|Stopwatch]]** -- Keep track of elapsed time.
  * **[[:panel-plugins:xfce4-systemload-plugin:start|Systemload]]** -- Displays the current CPU load, the memory in use, the swap space and the system uptime.
  * **[[:panel-plugins:xfce4-timer-plugin:start|Timer]]** -- Lets the user run an alarm at a specified time or at the end of a specified countdown period. 
  * **[[:panel-plugins:xfce4-time-out-plugin:start|Time-out]]** -- for taking breaks from the computer every X minutes.
  * **[[:panel-plugins:xfce4-verve-plugin:start|Verve]]** -- A comfortable command line plugin for the Xfce panel.
  * **[[:panel-plugins:xfce4-wavelan-plugin:start|Wavelan]]** -- Display stats from a wireless lan interface (signal state, signal quality, network name (SSID)). It supports NetBSD, OpenBSD, FreeBSD, and Linux. 
  * **[[:panel-plugins:xfce4-weather-plugin:start|Weather]]** -- Shows the current temperature and weather condition, using weather data provided by xoap.weather.com. 
  * **[[:panel-plugins:xfce4-whiskermenu-plugin:start|Whiskermenu]]** -- A menu that provides access to favorites, recently used, and searching installed applications. 
  * **[[:panel-plugins:xfce4-xkb-plugin:start|Xkb]]** -- Setup and use multiple (currently up to 4 due to X11 protocol limitation) keyboard layouts. 

----

Advanced
--------

  * **[[debugging|Debugging]]** -- Debugging plugins and the panel

----

Required Packages
-----------------

* `exo <https://gitlab.xfce.org/xfce/exo>`_
* `garcon <https://gitlab.xfce.org/xfce/garcon>`_
* `GIO <https://docs.gtk.org/gio/>`_
* `GLib <https://wiki.gnome.org/Projects/GLib>`_
* `GTK+ <https://www.gtk.org>`_
* `libxfce4ui <https://gitlab.xfce.org/xfce/libxfce4ui>`_
* `libxfce4util <https://gitlab.xfce.org/xfce/libxfce4util>`_
* libwnck
* `xfconf <https://gitlab.xfce.org/xfce/xfconf>`_


For specific information on the minimum required versions, check `configure.ac.in <https://gitlab.xfce.org/xfce/xfce4-panel/-/blob/master/configure.ac.in>`_

----

Latest Release
--------------

{{rss>https://archive.xfce.org/feeds/project/xfce4-panel 1 date description 2h}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfce4-panel/>`_

----

Source Code Repository
----------------------

https://gitlab.xfce.org/xfce/xfce4-panel

----

Reporting Bugs
--------------

* **[[:xfce:xfce4-panel:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

----

:start|Back to main Xfce documentation page
