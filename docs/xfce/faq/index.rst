=================================
Xfce - Frequently Asked Questions
=================================

.. Contents::

General Questions
*****************

How to pronounce Xfce ?
-------------------------

“Ecks Eff See Eee”

What does it mean ?
-------------------------

The name Xfce originally stood for XForms Common Environment, but since then, Xfce was rewritten twice and doesn't use XForms toolkit anymore. The name survived, but the F is no longer capitalized (not “XFce”, but “Xfce”). Currently the abbreviation doesn't stand for anything (suggestion: X Freakin' Cool Environment). It's not pronounced “X-Face”. There is no “a” in it.

What does the logo mean ?
-------------------------

A mouse, obviously, for all kinds of reasons like world domination and monsters and such.
    
On which platforms does Xfce run currently?
-------------------------------------------

Xfce is developed to be versatile. It is currently supported on Linux, Solaris and BSD, but has been known to run in some shape or form on IRIX, MacOS X, and Windows.

Under which license is Xfce distributed?
----------------------------------------

Xfce 4 components are licensed under free or open source licenses: GPL or BSDL for applications and LGPL or BSDL for libraries. Read the documentation, the source code, or the Xfce homepage for more information.

How long between two official releases?
---------------------------------------

There is no set schedule, but there are goals the developers try to meet. That said, the creation of deadlines does not lend itself well to those working without compensation. So the overall goal is to release a new version as certain goals are reached. Unfortunately, that does not allow the advanced statement of any release schedule. Please check back often to read any news releases about the product.

Where can I find Xfce information/support for my specific distribution?
-----------------------------------------------------------------------

If you are not able to find support on the Xfce Forums, you may want to use a site focused, specifically, on the distribution you are currently running. The following is not an exhaustive list of Xfce resources.

Distribution Specific Xfce Info/Support Pages:
----------------------------------------------

* ArchWiki
* Debian Xfce
* Fedora Xfce Desktop
* FreeBSD Xfce
    * FreeBSD Xfce FAQ
* Manjaro Xfce
* Linux Mint Xfce Forums
* Xubuntu
    * Ubuntuforums
    * AskUbuntu

General Xfce forum
------------------

* Xfce on Reddit


----

Keyboard Related
*****************

How to configure Shortcuts / Hotkeys / Menu Accelerators ?
----------------------------------------------------------

A number of Xfce applications (Thunar, for example) support the standard GTK2 way of changing shortcuts: simply hover over the menu option with the mouse pointer and press the keyboard shortcut you want to rebind it to.

To delete a keyboard assignment, press the **Backspace** key while you are on the menu entry.

If the shortcut doesn't change, then you need to enable the feature in GTK+. This can be achieved in 3 ways:

    * If you are running the Xfce desktop environment, enable **Editable menu accelerators** in the User Interface Preferences dialog.
    * If you are running GNOME then you can enable **Editable menu accelerators** in the **Menu and Toolbars** control center dialog.
    * Otherwise put the following in your ~/.gtkrc-2.0 file (create the file if it doesn't exist): ``gtk-can-change-accels=1``

.. warning:: When xfsettingsd is running you must change the setting with the Xfce GUI, not through the .gtkrc-2.0 file.

.. caution:: This functionality has been disabled since GTK3 which means that Xfce apps that have migrated to GTK3 (such as xfce4-terminal) do not support it. Refer to specific app's documentation to learn how to configure its shortcuts.

Is there some way to call the menu with the keyboard in Xfce?
-------------------------------------------------------------

Assign a key with the Keyboard ``Settings > Shortcuts`` to the command ``xfdesktop -menu``. (This does not work reliably since Linux Kernel is tickless, so xfdesktop -menu needs a fix) The menu will popup where your mouse is located. You can also use ``xfce4-popup-applicationsmenu`` to popup the panel menu (also provided by xfdesktop and make sure you have the plugin in your panel ^_~).

Is it possible to focus the Verve plugin with a key?
----------------------------------------------------

Assign a key to the command ``verve-focus``

My windows button does not work in the Keyboard Settings > Shortcuts.
---------------------------------------------------------------------

The windows button (also known as the superkey) not working as a modifier is related to the toolkit, GTK+ in the case of Xfce. If you want to have the windows-key working we recommend you to upgrade GTK+ to at least version 2.10.0.

How do I get numlock to start on login?
---------------------------------------

There are two possibilities to achieve this. Or you should use a display manager that turns the numlock on (eg. gdm, check the settings) or you can use a little program called numlockx, adding ``numlockx`` on in your .xinitrc will do the job.

Is it possible to use Media keys in the Shortcut Editor?
--------------------------------------------------------

Use ``xmodmap`` to assign keycodes to your Media keys to make them available for the Xfce shortcut editor:

To determine keycodes of the multimedia keys use the program ``xev``. Create a ``.Xmodmap`` file in your ``$HOME`` directory containing those keycodes and assign keysyms to them.

Here are some examples of keycodes and their respective keysyms:


.. code-block:: rst

    keycode 162 = XF86AudioPlay
    keycode 164 = XF86AudioStop
    keycode 160 = XF86AudioMute
    keycode 144 = XF86AudioPrev
    keycode 153 = XF86AudioNext
    keycode 176 = XF86AudioRaiseVolume
    keycode 174 = XF86AudioLowerVolume
    keycode 237 = XF86AudioMedia
    keycode 230 = XF86Favorites
    keycode 236 = XF86Mail
    keycode 178 = XF86WWW

All possible keysyms can be found in ``/usr/lib/X11/XKeysymDB`` or ``/usr/share/X11/XKeysymDB``. To ensure that the .Xmodmap file is loaded when you start Xfce add ``/usr/bin/xmodmap`` ``$HOME/.Xmodmap`` to your ``.xinitrc`` or ``.xprofile`` file. When you start the shortcut editor, the assigned keysyms should show up when you press one of your multimedia keys. Now it is possible to assign a command to them.

.. Note:: Several problems with auto-loading of ``.Xmodmap`` files at Xfce startup have been reported (also when issued as autostart command). Search the Xfce Bugzilla sites for current problems. As a workaround, run ``xmodmap ~/.Xmodmap`` by hand every time, or try out editing the somewhat less straightforward xkb configuration files.

How to determine keycodes with "xev"
--------------------------------------

All keyboards are different, keycodes can differ and not everyone has time to search XKeysymDB file. You can acquire keycodes manually from your keyboard using the application xev.

In a terminal type the following:

.. code-block:: rst

    xev | grep -A2 --line-buffered '^KeyRelease' | sed -n '/keycode /s/^.*keycode \([0-9]*\).* (.*, \(.*\)).*$/\1 \2/p'

Next, press the key that you need the keycode from(e.g. When the key “Stop” is pressed, the output is “174 XF86AudioStop”.

What should I do to change keyboard layout?
-------------------------------------------

There are several options. One is to use ``xfce4-xkb-plugin``, see xkb plugin . You can also use the ``setxkbmap`` command with the two letter keyboard code as argument; you can edit your X server configuration file to choose a different keyboard layout (change the value after ``Option “XkbLayout”``, e.g.: ``Option “XkbLayout” “dvorak”``).

Is it possible to change the default shortcut keys?
---------------------------------------------------

Yes, of course. Keyboard shortcuts are defined in two locations. The shortcuts to handle the window manager are defined in the Settings Manager > Window Manager Settings > Keyboard. The Default theme can not be changed; but, when you add a theme you can change that the theme you just added.

More global keyboard shortcuts, like volume adjustments, can be found in Settings Manager > Keyboard Preferences > Shortcuts. Again, you need to add a new theme before you can start customizing it.

How can I see a list of all the shortcut keys?
----------------------------------------------

Use the following command, which will produce a nicely formatted text list to standard output:

.. code-block:: rst

    xfconf-query -c xfce4-keyboard-shortcuts -l -v | cut -d'/' -f4 | awk '{printf "%30s", $2; print "\t" $1}' | sort | uniq

If you want to put this list into a file, add ``> filename`` at the end of command.

How do I make a shortcut that doesn't steal focus?
--------------------------------------------------

It is not currently possible to do this.

Back To Top

----

Application Menu
****************

The left-click to get the menu on the title bar menu button seems a little slow. How do I change that?
------------------------------------------------------------------------------------------------------

The left-button single-click menu button display speed is linked to the double click speed. If one wants the menu to appear quicker, just change the double click speed in the Xfce 4 Settings Manager Mouse properties to be faster. Or, one can right click on the title bar to get the menu displayed almost instantly without adjusting the double-click speed. The menu will display both ways.

How do I display a list of all windows?
---------------------------------------

There are two possibilities. The first is by middle clicking on the desktop (if you have xfdesktop running) or you can add the window list plugin to the panel (is provided with a ``xfce4-popup-windowlist`` command).

How to edit the auto generated menu with the menu editor?
---------------------------------------------------------

.. code-block:: rst

    cp ~/.cache/xfce4/desktop/menu-cache-name-of-the-generated-file.xml ~/.config/xfce4/desktop/menu2.xml
    cd ~/.config/xfce4/desktop/
    cat menu.xml > menu3.xml
    cat menu2.xml >> menu3.xml
    mv menu.xml menu.orig.xml
    mv menu3.xml menu.xml

Now, you already have a menu with all the categories in the main tree with some duplicates, but you must first edit menu.xml with your favorite editor and remove the 4 following lines in the middle of the file, otherwise the menu editor will complain about a wrong format:


.. code-block:: rst

    </xfdesktop-menu>
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE xfdesktop-menu>
    
    <xfdesktop-menu>

That's all. Now you can run the menu editor, remove the few duplicates and edit all as you like.

``Settings > Desktop > Menu > Menu Editor``

.. Note:: by removing the “system” line, you will remove all the duplicates menu entries from the auto generated file. So, if it is changed in this auto generated file, they don't appear anymore, but you will get rid of most of the duplicates.

To restore the original menu, just do in a terminal:

.. code-block:: rst

    mv menu.xml menu3.xml; mv menu.orig.xml menu.xml

What are the exact commands used when launching the 'Settings' applications?
----------------------------------------------------------------------------

Please see this wiki entry for a list of the precise commands run for each entry under the 'Settings' menu in a default installation of Xfce4.

Back To Top


----

Desktop Manager
***************

I want to disable the trash, home and filesystem icons on my desktop, is that possible?
---------------------------------------------------------------------------------------

Yes. In Settings > Desktop > Icons > Appearance, select 'None'.

My Xfce Desktop doesn't have any shortcut icons, why?
-----------------------------------------------------

You can adjust this via Settings > Desktop > Icons > Appearance.

Back To Top


----

Panel
*****

Is it possible to change the icon used by the icon box or task bar for a given application?
-------------------------------------------------------------------------------------------

It's not possible. This setting has to be managed by the application itself.

I've installed a plug-in for the panel, but the indicators don't use different colors. What can I do?
-----------------------------------------------------------------------------------------------------

First, try another Gtk theme, since some themes override the color. If it doesn't solve the problem, you probably have an old ~/.gtkrc-2.0 : remove it and try again.

How do I set the panel layer in Xfce 4.2 and 4.4?
-------------------------------------------------

In order to improve focus management this option was removed.

Is there a world clock applet?
------------------------------

You need to add the Orage Clock to the panel. Then you can middle-click the clock to open the “Global Time” window, to which you can add any number of clocks.

Back To Top


----

Themes
******

The gtk-xfce-engine themes do not appear in the "user interface" settings dialog
--------------------------------------------------------------------------------

The gtk-xfce-engine-2 package has to be installed using same prefix as Gtk2 itself. When installed from sources, the engine is, by default, installed in ``/usr/local``, while Gtk2 is often installed in /usr. Just install gtk-xfce-engine-2 again using ``./configure –prefix=/usr``, and the themes will hopefully become available.

How can I customize my Xfce desktop environment
-----------------------------------------------
You can read everything about changing themes in the How to install new themes wiki page.See Xfce Look for a selection of themes geared towards Xfce/Xfwm4.

Where can I find additional backgrounds and wallpapers for my desktop?
----------------------------------------------------------------------

Here is a selection of beautiful images and pointers to other sites with quality, high-resolution images.

Back To Top


----

Miscellaneous
*************

Why the file chooser is very slow ?
-----------------------------------

It is more likely that the icon theme you are using renders too many SVGs making it very hard to scroll. Switch to another icon theme.

Why the response to Terminal application is slow?
-------------------------------------------------

For NVidia users, add this to your settings:

.. code-block:: rst

    nvidia-settings -a InitialPixmapPlacement=0 -a GlyphCache=1

For all users, your driver may not support argb visuals very well. You can disable it for Terminal by exporting the environment variable ``XLIB_SKIP_ARGB_VISUALS=1``. To disable it for Terminal only, put the next lines inside ``~/bin/Terminal`` for example (given you have a personal bin directory, you can also put it inside ``/usr/local/bin``):

.. code-block:: rst

    #!/bin/sh
    XLIB_SKIP_ARGB_VISUALS=1 /usr/bin/Terminal

How do I enable panel transparency and window shadows?
------------------------------------------------------

Enable the Composite extension in the X11 config file and make sure Xfwm4 is compiled with embedded compositor (``xfwm4 -V``).

.. code-block:: rst

    Section "Extensions"
        Option "Composite" "Enable"
    EndSection


Pay attention: recent versions of X.org turn composite on by default. If you experience speed problems or any other glitches you have to disable it explicitly:

.. code-block:: rst

    Section "Extensions"
        Option "Composite" "Disable"  
    EndSection

If you have a reasonably new X.org (7.1, possibly 7.0) and your graphics card is listed as “supported” at X.org's EXA status page, you should also enable EXA by adding this line to the card's Device section in your xorg.conf:

.. code-block:: rst

    Option "AccelMethod" "exa"


Enabling EXA will normally provide a speed increase for compositing and font rendering, but may cause a small reduction in OpenGL rendering speed.

Once the Composite extension is activated, go to ``Settings > Panel`` and ``Settings > Window Manager Tweaks``.

ATI users (X.org radeon driver)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ATI R3xx/R4xx (9500 to X850, X1050) users may also need this in the device ``section`` for the card:

.. code-block:: rst

    Option "MigrationHeuristic" "greedy"
    Option "AccelDFS" "true"			# but see radeon(4)
    Option "EnablePageFlip" "true"
    Option "EnableDepthMoves" "true"


nVidia users
^^^^^^^^^^^^

NVidia users may also need this in the device section for the card:

.. code-block:: rst

    Option "RenderAccel" "true"
    Option "AllowGLXWithComposite" "true"


Read ``/usr/share/doc/nvidia-glx/README.txt.gz`` (and search for “RenderAccel” and “AllowGLXWithComposite”) to see if they are recommended at all for your system. At least for recent NVidia GLX drivers, “AllowGLXWithComposite” “true” is only for X servers older than X11R6.9.0, and “RenderAccel” “true” is the default setting, and therefore not required. If you are running a recent NVidia driver and a recent xorg-server, you do not need these settings (and should not use the “AllowGLXWithComposite” “true” setting).

Kiosk - I want to use Xfce in a corporate environment and not let users modify their menu.
-----------------------------------------------------------------------------------------------

Use kiosk mode (see also xfce4-session docs).

How to use a different Window Manager
-------------------------------------

Please refer to this manual page for instructions and caveats regarding the running of a Window Manager other than fvwm4.

How to use SCIM in Xfce
-----------------------

Refer to this manual

On Login: When I start Xfce a dialog pops up saying "Could not look up internet address for..."
-----------------------------------------------------------------------------------------------

Xfce simply wants your hostname to be in ``/etc/hosts``. Example input: ``127.0.0.1 localhost``

On Logout: When I try to log out by pressing the logout button in the panel, I get a dialog asking me whether I want to quit the panel and/or xfce4-session-logout reports that no session manager is running, but it is!
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
For some reason, your X applications can not connect to the session manager.

Possible causes are:
    * Your hostname cannot be resolved (see Login problems section).
    * Your home partition or partition containing /tmp is filled up.
    * Your hostname contains non-ascii characters (no umlauts allowed, in particular)
    * Either ``~/.ICEauthority`` or ``/tmp/.ICE-unix`` has wrong permissions.

Also check ``.xsession-errors`` for clues.

How can I install a new font in Xfce?
-------------------------------------

Refer to your distribution-specific support as this is handled by your distro and not, specifically Xfce.

