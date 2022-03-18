************************
Bug Reporting and Fixing
************************

One of the most useful tasks that we rely on the community for is the testing and reporting of bugs. Since Xfce runs on various platforms and in a variety of different setups, testing all changes, in every possible situation, is an impossible task. As such, we kindly ask our users to assist us in testing, and reporting all bugs that they may find, using our `issue tracker <https://gitlab.xfce.org>`_.

  * **[[:contribute:bugs:bug-summary|Current Xfce open bugs]]**

----

Crashes
=======

We always try to make the software as stable as possible, but there is always a possibility a crash or segfault can occur. To problem with crashes is that they are not always reproducible by the developers, this often makes it quite hard to track-down the problem and patch the issue.

Nonetheless, there are a couple of things you can do to help resolve them.

----

Search First
============

Search the `Open Bug Summary <https://docs.xfce.org/contribute/bugs/bug-summary>`_ to see if the issue is already known. Also, look through the resolved bugs because the issue might be fixed already, but has not been released or applied downstream. Peeking the `GIT repository <https://gitlab.xfce.org>`_ might help for the latter.


* For a list of currently open bugs, see the [[:contribute:bugs:bug-summary|open bugs summary]].

----

Report
======

When writing your bug report, try to be as descriptive as possible, but avoid verbosity; Mozilla has a nice guide on `how to write a bug report <https://developer.mozilla.org/en-US/docs/Mozilla/QA/Bug_writing_guidelines>`_.

If you have not found anything or missed it, report it in the bug tracker. Reports that only say `application X crashed` will be closed as invalid quickly, so try to provide a way to describe and reproduce the problem: `Application X crashed when doing Y`.

In the description provide a short way to reproduce the crash. Also run the application in a terminal and look if there are console warnings, put those in the bug as well.

If the developer cannot reproduce it, he might ask for a `backtrace`, read more about creating backtraces in the next section.

Back To Top

----

Backtraces
==========

If you do get an Xfce application to crash, it's best to detail exactly what you were doing that led to the crash. In addition, we need the //backtrace// of the crash. However most distributions by default make backtrace output useless because there binaries are optimized and do not contain human-readable information to make a relation between the compiled code and the source code (like file, function and variable-names).

The sites below provide guidance from the respective distributions how to remedy this situation so you can provide all the info we need to fix your issue.

In case of panel plugins there is some additional information on [[:xfce:xfce4-panel:debugging|how to start a panel plugin inside a debugger]].

  * https://wiki.archlinux.org/title/Debugging/Getting_traces
  * https://wiki.debian.org/HowToGetABacktrace
  * https://wiki.ubuntu.com/DebuggingProgramCrash
  * http://wiki.gentoo.org/wiki/Project:Quality_Assurance/Backtraces
  * http://fedoraproject.org/wiki/StackTraces
  * https://wiki.mageia.org/en/Debugging_software_crashes
  * http://wiki.mandriva.com/en/Development/Howto/Software_Crash
  * http://en.opensuse.org/openSUSE:Bugreport_application_crashed
  * https://wiki.sabayon.org/?title=Debugging_Symbols_-_splitdebug

Back To Top

----

Fixing Bugs
===========

Once a bug has been found, the cause of the bug needs to be tracked down, and then (obviously) fixed. If you want to get involved in the actual development process of Xfce a great way to start is by solving bugs and attaching a patch file to the reported bug. ( "git format-patch" is the preferred way to create a patch file ) 

Not familiar with git? [[contribute/dev/git/start|This manual]] will help you to get started. 

To get started, best read our [[contribute/dev/coding/example|beginners example on how to fix a simple xfce bug]].


Back To Top

----

start:|Return to Main Xfce documentation page