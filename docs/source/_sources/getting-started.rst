*************************
Getting Started with Xfce
*************************

* Installation
* Running Xfce
* The Desktop Environment
* Common Tasks
* Further Reading

Introduction
============
Xfce is a lightweight desktop environment for Unix-like operating systems. It aims to be fast and light on system resources, while still being visually appealing and easy to use.

Xfce embodies the traditional UNIX philosophy of modularity and re-usability. It consists of a number of components that provide the full functionality one can expect of a modern desktop environment. They are packaged separately and you can pick among the available packages to create the optimal personal working environment.

Another priority of Xfce is an adherence to standards, specifically those defined at freedesktop.org.

System Requirements
-------------------

Even though Xfce is very light-weight, there are some distribution specific minimum requirements.

Installation
============

The Xfce project officially only releases source code for the desktop environment. However, binary packages may have been contributed by other people for your OS or distribution. Here some links to distribution specific installation instructions:

* Arch
* Debian
* Fedora
* FreeBSD
* Gentoo
* Mageia
* MidnightBSD ( or possibly ``pkg_add -r xfce4`` ? )
* Mythbuntu: sudo apt-get install mythbuntu-desktop
* NetBSD (pkg_add xfce4)
* Ubuntu: sudo apt-get install xubuntu-desktop (package description; direct install)

Detailed instructions on compiling Xfce yourself can be found here.

Running Xfce
=====================

* Display Managers

Xfce4-session installs a file that should add an option for display managers to run an Xfce session. The Xfce Desktop Environment does not have its own DM, but various options are available like gdm, slim, lxdm and lightdm. Check this link for details.

* Command line

Use startxfce4 to start an Xfce session or choose Xfce Session from the login manager, which includes the session manager, the panel, the window manager and the desktop manager. See auto login from console for more information.

By default, the Xfce session manager manages the startup of applications. It allows you to save your session when you quit Xfce, so that the next time you log in, the same applications will be started for you automatically.

The Desktop Environment
=======================

The Xfce Desktop Environment is not a single entity that provides all functionality, but rather it tries to adhere to the old UNIX tradition of small tools that do one job and do it well.

Default Xfce session, with desktop manager and panel

When you start the Xfce session for the first time, several applications are started by the Xfce session manager:

* Panel
    In a default session there is a full width panel at the top of the screen and a smaller one at the bottom. The Panel application manages all panels on the screen.
    The top panel shows a graphical pager with a miniature view of all workspaces, a task list showing all applications running on the current workspace and a system tray to show status icons that are used for example by some media players or instant messaging applications.
    The bottom panel contains several application launchers and a clock. You can right-click on any panel item to get a menu that allows you to change its properties, add or remove new items or to change the properties of the panel itself.
* Desktop Manager
    The desktop manager provides the desktop background image and two menus when you click on the desktop background. Optionally, it can show icons on the desktop, either for minimized applications or for files in the ~/Desktop folder.
    The right mouse button opens a menu that allows you to start applications. Look at the manual to find out how to change the menu contents.
    The middle mouse button (or Shift + left click) opens a list of all applications that are currently running. You can activate an application by clicking on its menu entry.
* Window Manager
    The Window Manager is responsible for placing the windows on the screen and provides the window borders and decorations. It allows you to move windows around by dragging the title bar, and provides title bar buttons: for example to close, minimize or maximize a window. Look at the manual for a detailed explanation of the window manager settings.
* Settings Manager
    The settings manager runs in the background and ensures that all Xfce applications update their settings when the user changes something within the application. It is also responsible for reading the configuration files on disk at startup. Look at the manual for a detailed explanation of the settings manager.

Common Tasks
================

This section will explain how to perform several common tasks to quickly get you started working with Xfce and familiar with its applications.

Running Programs
----------------

* Xfce Panel
    The panel can be used to allow quick access to your most frequently used applications by means of launchers, these application launchers are displayed as icons on your panel that launch your specified program. The Applications Menu on the panel also contains all installed programs.
* Desktop Menu
    Another method for starting applications is from the desktop right-click menu. Read the Desktop Manager manual for more information on how to change the menu contents.
* Application Finder
    If you know the name of the application you want to launch you can use the Application Finder. To open the dialog, press Alt-F2 or choose the Run Program... option from the desktop menu.

Managing Windows and Workspaces
-------------------------------

* Basic window operations
    You can move a window around the screen by dragging on its title bar. A window can be closed, minimized, maximized, shaded and made sticky (make it show up on all workspaces) by using the title bar buttons.
    Right-clicking on the title bar will open a menu that gives access to all window operations.
    Shading a window, or rolling it up to hide its contents and only show the title bar, can also be accomplished by scrolling the mouse wheel while hovering over the title bar. Mouse wheel up is shade, mouse wheel down is unshade.
    If you don't want maximized windows to cover up the entire screen, you can set workspace margins in the Settings Manager.

* Application management
    To see what applications are currently running, you can look at the task list on the panel. Clicking on an application in the task list will focus it, and clicking it again will hide it.
    When you click with the middle mouse button on the desktop background a list of windows is shown, ordered by workspace. You can activate the application or change workspaces by choosing the appropriate menu entry.

* Workspaces
    You can change workspaces by clicking on them in the graphical pager on the panel. Pressing Ctrl-Alt-LeftArrow or Ctrl-Alt-RightArrow will cycle through the workspaces. Scrolling the mouse wheel while hovering over the pager or the desktop background has the same effect.
    To add or remove workspaces, you can use the middle-click desktop menu or the settings dialog (see below).

Using the Settings Manager
--------------------------

The Settings Manager provides access to the global preferences of many aspects of the Xfce Desktop Environment. You can run it by pressing its launcher on the panel, from the desktop mouse menu or by running xfce4-settings-manager.

Refer to the individual manuals of the Xfce components for more information on settings specifically for that application. Don't be afraid to explore all the settings to find out what options are available that allow you to create the best possible working environment.

Further Reading
===============

This guide provides only a general overview of the Xfce Desktop Environment. More information is available in the manuals of the individual components of Xfce. 
