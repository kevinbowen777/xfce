=========================
Building Xfce from source
=========================

 .. 206 backtraces

To compile a complete Xfce desktop from source requires some information about the dependency chain and the various configure options available in each module. This page will describe this in detail, so you can compile your own Xfce desktop; both system wide as well as in your $HOME directory.

.. Contents::

----

Choosing your Xfce version
--------------------------

First you will need to decide on which version of Xfce that you want to compile. Xfce version numbers are constructed like this: 1.2.3 => major.minor.micro. If the minor version is an even number, this means that it is a stable release. An odd numbered minor version indicate a development, or testing snapshots. The micro number increases with each release. Also, it is recommended to keep the major.minor version the same for the core components (some packages don't follow those numbers) or there will most likely be dependency version problems during compilation.

The latest releases available can be found on the `download <https://www.xfce.org/download>`_ page. You can also build from the source repositories if you have enough experience. Additional information about this is provided below.

----

Obtaining the Xfce source code
------------------------------

Once you have decided which version that you want to compile, there are a couple of ways to download the source code. You can either choose to build official released packages, or clone the source repositories. Choosing the released packages is the recommended option. The source repositories could possibly be broken and are not generally suitable for production environments. However, they always contain the latest features, bug fixes and translations.

If you are not sure which to choose, it is easiest to begin with the latest stable fat-tarball of a collection release.

Released packages
^^^^^^^^^^^^^^^^^

Xfce packages have two types of releases: collection releases and individual releases. Click the links below to open the relevant download location.

* `Collection releases of the core modules <https://archive.xfce.org/xfce/>`_
  From time to time a new collection release of Xfce is made. A collection release consists of a number of individual tarballs and a fat-tarball that contains all of the individual tarballs.
  The collection releases always contains the correct versions needed to build the other packages in the release. If you want the latest version of each package, you can start with a collection release and then look for individual bug fix releases, explained in the item below. 
* `Individual releases <https://archive.xfce.org/src/xfce/>`_
  Each package in Xfce is allowed to make development and stable releases at any time, see the `release model <http://xfce.org/about/releasemodel>`_ documentation for more information. 

From the code repository
^^^^^^^^^^^^^^^^^^^^^^^^

For the latest code, you need to make local copies of the `GIT repositories <https://gitlab.xfce.org/>`_. This is the place where developers submit their code. If you decide to use GIT, try to use the same branch for all the packages to avoid dependency version problems.

.. Note:: For additional information about using Git with Xfce, see the `Xfce and git information <https://docs.xfce.org/contribute/dev/git/start>`_ page.

You first need to make clones of each GIT repository, like the command below, where ``$category`` is for example ``xfce`` and ``$module`` ``xfce4-panel``. If you click on a module in the `online repository <https://gitlab.xfce.org/xfce>`_ list, the clone uri is shown at the bottom of the page.

.. code-block:: rst

    git clone https://gitlab.xfce.org/$category/$module

After the repository is cloned, you will need to choose which branch you want to compile. By default, the ``master`` branch is selected, but there are also branches for stable releases like ``xfce-4.16``. The stable branches contain the latest bug fixes without any major new features, the master branch is the development version for the next release of Xfce. Both should not be used in a production environment.

To switch to another branch (``git branch -a`` lists all available branches) run the following command inside the cloned directory to switch to, for example, the ``xfce-4.16`` branch:

.. code-block:: rst

    git checkout --track origin/xfce-4.16

After this, you can update your local copy of the repository with git pull and switch to another branch with ``git checkout $branchname``. Read the `GIT manuals <https://git-scm.com/doc>`_ for more information about using GIT.

Back To Top

----

Xfce Dependencies explained
---------------------------

Build requirements
^^^^^^^^^^^^^^^^^^

Before you can start compiling, you need a couple of packages that are required to compile Xfce. Use your distributions package manager to install those packages. Additional packages are required too for some modules, but we'll get to that later.

* `A working GNU toolchain <https://en.wikipedia.org/wiki/GNU_toolchain>`_
* Gtk+ and Glib headers, in some distributions called the -devel packages 
    * Xfce 4.14 requires Gtk+ 3.22 and Glib 2.50
    * pkgconfig
    * Coffee or tea


For history, here are the versions needed for older xfce releases, which are not supported anymore

* Xfce 4.16 requires Gtk+ 3.22 and Glib 2.42
* Xfce 4.12 requires Gtk+ 2.24 and Glib 
* Xfce 4.10 requires Gtk+ 2.20 and Glib 2.24
* Xfce 4.8 requires Gtk+ 2.14 and Glib 2.20
* Xfce 4.6 requires Gtk+ 2.10 and Glib 2.12


Xfce's dependency chain
^^^^^^^^^^^^^^^^^^^^^^^

The Xfce packages need to be built in a specific order. If you don't follow this, compile options might not be available or the configure stage will abort because of missing dependencies.

* xfce4-dev-tools (only required if you build from GIT)
* libxfce4util
* xfconf
* libxfce4ui
* garcon, exo
* thunar
* xfce4-panel, xfce4-settings, xfce4-session, xfdesktop, xfwm4, xfce4-appfinder, tumbler...

Package specific dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Some core packages in Xfce have additional or optional dependencies, all are listed in the table below for the latest stable version. We only show the top-dependency (so xfce4-panel also requires gtk+, but libxfce4ui already depends on that).

.. tip:: Note that some of the package-names may vary between distributions.

.. csv-table::
   :header: "", "Dependency(-ies)", "Optional Dependency(-ies)"
    
    "xfce4-dev-tools", "autoconf, automake, intltool, pkgconfig"
    "libxfce4util", "glib2"
    "xfconf", "libxfce4util, gdbus"
    "libxfce4ui", "libxfce4util, gtk+, xfconf, glibtop", "libstartup-notification, libgladeui"
    "garcon", "gio, libxfce4util"
    "exo", "libxfce4util, gtk+, perl-uri, libxfce4ui"
    "xfce4-panel", "libxfce4ui, exo, garcon, libwnck", "libstartup-notification"
    "thunar", "libxfce4ui, exo, libpng, gtk+, glib", "libexif, gdbus, libnotify, libstartup-notification, freetype, libjpeg, libxfce4panel, xfconf"
    "xfce4-settings", "libxfce4ui, exo, xfconf, gdbus, libXi, libXrandr", "libXcursor, libnotify"
    "xfce4-session", "libxfce4ui, perl-xml-parser, libwnck, gdbus"
    "xfwm4", "libxfce4util, libxfce4ui, libxfconf, gdbus, libwnck", "libstartup-notification"
    "xfdesktop", "libxfce4ui, xfconf, libwnck, exo garcon", "thunarx, garcon, libnotify"
    "xfce4-appfinder", "libxfce4ui, garcon, gio"
    "tumbler", "dbus-glib, gio, gmodule, gdk-pixbuf", "freetype-config (fonts), jpeg (jpeg thumbnails from exif), libffmpegthumbnailer (video), gstreamer-1.0 (video), poppler-glib (pdf), libgsf (odf), libopenraw-gnome (various raw images)"

Back To Top

----

Building the packages
---------------------

Installation location and variables
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now it is finally time to start compiling the Xfce desktop. Last remaining thing is to choose an installation location. Possible examples are ``/usr``, ``/usr/local`` and ``/opt/xfce4`` for a system-wide installation or ``$HOME/local`` if you want to install in your home directory (whatever you choose, never put spaces in the name). We will refer to this location as ${PREFIX} in the code examples below!

You need to make sure the ``PKG_CONFIG_PATH`` variable include the path to the *.pc files installed by the Xfce libraries:

.. code-block:: rst

    export PKG_CONFIG_PATH="${PREFIX}/lib/pkgconfig:$PKG_CONFIG_PATH"

You can also set some optimization flags for the compiler. This may speed up Xfce, but can also make debugging impossible on some systems. Even worse, this can also cause gcc to generate broken code, so be careful with this. The line below should be safe for most system.

.. code-block:: rst

    export CFLAGS="-O2 -pipe"
 
If you want a debugging environment, unset the CFLAGS and use ``--enable-debug``, see below for the different debug levels.

.. code-block:: rst

    export CFLAGS=""
  
Compiling and installing
^^^^^^^^^^^^^^^^^^^^^^^^

Next step is compiling the various packages following the dependency chain above. If you have downloaded the tarballs, you will need to unpack them before going on. Inside each package directory you should run the following command:

.. code-block:: rst

    ./configure --prefix=${PREFIX} && make && make install

To build from GIT you need to install the xfce4-dev-tools package first, all other packages should be installed with this command:

.. code-block:: rst

    ./autogen.sh --prefix=${PREFIX} && make && make install

Specific configure options for each package can be shown with ``./configure --help``. Note that most packages will see a performance benefit if passed the configure option ``--disable-debug``. 

However, if you want to provide backtraces or test new code, no ``$CFLAGS``, no binary stripping and ``--enable-debug=full`` are recommended. Please note that ``--disable-debug`` is not available for xfce4-dev-tools.

.. Note:: When reusing the ``./configure`` script while building from GIT remember to pass the flag ``--enable-maintainer-mode``.

If you install the package in a public prefix, for example ``/usr`` or ``/usr/local``, you will need to run ``make install`` using sudo. This way, you will be asked for the system administrator password and will have write permissions to install in those locations.

.. code-block:: rst

    sudo make install

Understanding Debug levels
^^^^^^^^^^^^^^^^^^^^^^^^^^

Most Xfce modules use the m4 macro **XDT_FEATURE_DEBUG** to manage the debug compiler levels. If so there are a number of options possible for ``--enable-debug=``

no
~~~
  Cast checks and asserts in the Glib macros are disabled, this might be a tad faster, but it can results in segfaults and unexpected crashes.

minimum
~~~~~~~
  This is the same as ``--disable-debug``. No additional compiler options are added, but checks in Glib are not disabled. This is the recommended level for users and distributions. 

yes
~~~
  A number of ``$CFLAGS`` are set to check the code for different errors. During configure you'll see all the options are tested to avoid binaries that do not work.

full
~~~~
  Same as the level above, including ``-Werror`` so the compilers aborts during compiler errors. The compiler will also generate binaries with debug information suitable for [[:contribute:bugs:|backtraces]] and memory checks. This is the recommended level for developers or users who want to report bugs.

Back To Top

----

Finding additional Help
-----------------------

Hopefully everything went fine after reading this guide. If you still have problems or questions you can ask on the `Xfce users mailing list <https://www.xfce.org/community#mail>`_, the `forum <https://forum.xfce.org>`_ or ask distribution related questions on their forums and mailing lists.

Have fun building Xfce!

Back To Top

----

start|Back to main Xfce documentation page