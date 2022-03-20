***************
xfce4-dev-tools
***************

.. Contents::

----

The Xfce development tools are a collection of tools and macros for
Xfce developers and people that want to build Xfce from Git In addition
it contains the Xfce developer's handbook.


----

xfce-build containerized build environment
==========================================

This project also contains the code to build and deploy xfce-build to the
`xfce-build area on Docker Hub <https://hub.docker.com/repository/docker/xfce/xfce-build/>`_.
This container is the build environment used by Xfce to build the various projects.
It can also be used as your own build environment as follows:

.. code-block:: rst

    docker run --rm -u $(id -u ${USER}):$(id -g ${USER}) \
    --volume $(pwd):/tmp xfce/xfce-build:master /bin/bash \
    -c "cd /tmp; ./autogen.sh && make distcheck"

The steps to build the container are encoded in the [`Dockerfile`](Dockerfile) in
this repository, and is built via the build job in [`.gitlab-ci.yml`](.gitlab-ci.yml).

----

CI templates for Xfce
=====================

The [CI folder](ci/) contains the ``build_project.yml`` template for building the various
Xfce projects, as well as supporting scripts such as ``build_libs.sh`` which handles
building any needed dependencies. This helps us avoid repeating the same build
code in each project.

----

Release notes for 4.15.0
========================

[Please note that this is a development release.]

- New macro XDT_VERSION_INIT(SEMVER[, TAG])

This macro takes care of setting up the version numbering.
It will define the following macros based on SEMVER and TAG:

   - xdt_version
   - xdt_version_major
   - xdt_version_minor
   - xdt_version_micro
   - xdt_version_tag
   - xdt_version_build
   - xdt_debug_default

If TAG isn't specified, the xdt_version_tag and xdt_version_git
will be empty and xdt_debug_default will be set to "minimum",
otherwise the xdt_version_build will contain a git hash and
xdt_debug_default will be set to "yes"

Example usage:

.. code-block:: rst

    XDT_VERSION_INIT([4.15.3],[git])
    AC_INIT([xfce4-someproject], [xdt_version()])
    ...
    XDT_FEATURE_DEBUG([xdt_debug_default])


- XDT_I18N macro will now automatically find the linguas if none are
specified during the autoconf run.

- Install m4 macros in default search dir. This makes autoconf find the
macros by default.

By setting version via XDT_VERSION_INIT and using XDT_I18N without
arguments,
this is no longer necessary to use a separate configure.ac.in and a
plain configure.ac can be used !
A big thank to Natanael Copa (ncopa) for his work on this part !

- xfce4-dev-tools now also handle the CI (docker container,
.gitlab-ci.yml templates files etc) on our new gitlab instance. A merge
request or a push to master to any of our projects automatically trigger
a build. This will help us to catch errors quicker and have better
quality. Thanks to Jason Yavorska and Simon Steinbeiss.

- New helpers are also available (xfce-get-release-notes,
xfce-get-translations, xfce-update-news) to help our maintainers to do
releases

Back to Top

----

Latest Release
==============
{{rss>https://archive.xfce.org/feeds/project/xfce4-dev-tools 1 date description}}

`Previous Releases <https://archive.xfce.org/src/xfce/xfce4-dev-tools/>`_

Back to Top

----

Source Code Repository
======================

https://gitlab.xfce.org/xfce/xfce4-dev-tools

----

Reporting Bugs
==============

* **[[:xfce:xfce4-dev-tools:bugs|Reporting Bugs]]** -- Open bug reports and how to report new bugs

Back to Top

----

:start|Back to main Xfce documentation page