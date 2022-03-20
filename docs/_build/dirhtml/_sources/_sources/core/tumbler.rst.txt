~~NOTOC~~
{{ :xfce:xfce.tumbler.png?no link|}}
====== Tumbler - Thumbnail Service ======

  * **[[#Introduction|Introduction]]**
  * **[[#Configuration|Configuration]]**
  * **[[#Available Plugins|Available Plugins]]**
  * **[[#Standards compliance|Standards compliance]]**
  * **[[#Debugging Support|Debugging Support]]**
  * **[[#Required packages|Required packages]]**
  * **[[#Latest Release|Latest Release]]**
  * **[[#Source Code Repository|Source Code Repository]]**
  * **[[#Reporting Bugs|Reporting Bugs]]**

----

===== Introduction =====

Tumbler is a D-Bus service for applications to request thumbnails for
various URI schemes and MIME types. It is an implementation of the
thumbnail management D-Bus specification described on 

[[https://wiki.gnome.org/DraftSpecs/ThumbnailerSpec]]

written in an object-oriented fashion using GLib and GObject. Its
modular architecture makes it very flexible and useful in many
situations. It provides plugin interfaces for extending the URI schemes
and MIME types for which thumbnails can be generated as well as for replacing the storage backend that is used to store the thumbnails
on disk. Tumbler's functionality can also be extended via specialized
thumbnailer services implemented in accordance to the thumbnail
management D-Bus specification.

Tumbler is used by Thunar, Ristretto, Xfce.

----

===== Configuration =====

You can override the default cache directory ''$HOME/.cache'' in which, besides other non-essential files, thumbnails are stored:


  * **D-Bus/ systemd**
     * create a file below ''~/.config/environment.d/'' and inside set XDG_CACHE_HOME. E.g:
     * ''XDG_CACHE_HOME=$HOME/.my_new_cache''

  * **Other**
     * Extend  $HOME/.profile, $HOME/.bash_rc or similar
     * ''export XDG_CACHE_HOME=$HOME/.my_new_cache''

After that, re-login, make sure the variable is set, and check if it works fine.

Tumbler has a configuration file ''tumbler.rc'' described in a [[available_plugins#configuration|dedicated page]].

----
===== Available Plugins =====

Tumbler allows to load a number [[:xfce:tumbler:available_plugins:|additional tumbler plugins]] to support different file formats. Most plugins are loaded by default, if the required libraries are provided. 

----

===== Standards compliance =====


Tumbler supports and implements the following standards/specifications:
  * [[https://standards.freedesktop.org/basedir-spec/basedir-spec-latest.html|XDG Base Directory Specification]]
  * [[https://specifications.freedesktop.org/thumbnail-spec/thumbnail-spec-latest.html|Thumbnail Managing Standard]]
  * [[https://wiki.gnome.org/DraftSpecs/ThumbnailerSpec|Thumbnail Management D-Bus Specification]]
  * [[https://www.freedesktop.org/wiki/Specifications/file-uri-spec/|File URI Specification]]

[[|Back To Top]]
----

===== Debugging Support =====


Tumbler currently supports four different levels of debugging support, 
which can be setup using the configure flag `--enable-debug' (check the 
output of `configure --help'):

  `full'  Use this if you want to debug Tumbler to locate a bug. The
    build will most probably be noticably slower. This is also
    recommended for people that want to develop Tumbler stuff.

  `yes'  This is the default for git snapshot builds. It adds all
    kinds of checks to the code, and is therefore likely to run
    slower. Use this if you want to develop for Tumbler (e.g.
    writing Tumbler extensions and such).

  `minimum'  This is the default for release builds, and presents the
    recommended behaviour.

  `no'  Disables all sanity checks. Don't use this unless you know
    exactly what you do.

[[|Back To Top]]
----

===== Required packages =====

Tumbler depends on the following packages:

  * GLib >= 2.50.0

Tumbler can optionally use the following packages:

  * gdk-pixbuf >= 2.14.0 (various image formats, some of them requiring the installation of optional libraries specific to gdk-pixbuf; also required for all other plugins below) 
  * FreeType >= 2.0.0 (font)
  * FFmpegthumbnailer >= 2.0.0 (video)
  * GStreamer >= 1.0.0 (video)
  * Poppler >= 0.12 (PDF/PS)
  * libgsf >= 1.14.9 (ODF)
  * libopenraw >= 0.0.4 (RAW images)
  * libpng >= 1.2.0 (for the Thumbnail Managing Standard storage backend)
  * libgepub >= 0.6.0 (EPUB)

[[|Back To Top]]
----

===== Latest Release =====
{{rss>https://archive.xfce.org/feeds/project/tumbler 1 date description 2h}}

[[https://archive.xfce.org/src/xfce/tumbler/|Previous Releases]]

[[|Back to Top]]

----

===== Source Code Repository =====

[[https://gitlab.xfce.org/xfce/tumbler]]

----
===== Reporting Bugs =====

  * **[[:xfce:tumbler:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

[[|Back To Top]]
----
[[ :start:|Return to Main Xfce documentation page]]