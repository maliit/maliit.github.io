---
title: Installing
layout: page
---

__Old information from [maliit.org](https://web.archive.org/web/20111031073411/http://wiki.maliit.org/Documentation/Installing) Needs to be updated__

If you just want to use Maliit or develop third party plugins, we recommend using the provided packages. If you want to develop on Maliit itself, we recommend installing from source.

When you have installed, go to Documentation/Running

## From source code (all GNU/Linux)

Grab the source source code from git:

* Maliit framework:
{% highlight bash %}
git clone git@gitorious.org:maliit/maliit-framework.git
{% endhighlight %}

* Maliit plugins (virtual keyboards etc.):
{% highlight bash %}
git clone git@gitorious.org:maliit/maliit-plugins.git
{% endhighlight %}

The installation order is
* maliit-framework
* maliit-plugins

Maliit uses the qmake build system. So, to do a standard build and install, do:

{% highlight bash %}
qmake
make
make install
{% endhighlight %}

Run qmake HELP=1 to get more information about build options.

__Dependencies__

All components have a hard dependency on Qt 4.7

## From source code (Windows)

Note: Windows support for Maliit is very experimental. Loading the IM plugins inside Maliit Server currently crashes: MALIIT#111

These instructions require Maliit 0.90.1 or newer

### Prerequisites

* Qt SDK 1.1+ (recommended) or Qt 4.7+ Mingw libraries. Download: http://qt.nokia.com/downloads
* git and sed/tr/cat. Download: http://code.google.com/p/msysgit/downloads/list
* pkg-config. Download: http://www.gtk.org/download/win32.php (depends on gettext-runtime and glib)

### maliit-framework
* Make sure that all the prerequisites exist in the PATH.
* Use the following arguments to qmake:
CONFIG+=disable-gconf CONFIG+=disable-dbus CONFIG+=nosdk CONFIG+=nodoc CONFIG+=notests PREFIX=C:/Maliit LIBDIR=C:/Maliit/bin
* Do qmake, make, make install

### maliit-plugins
* Make sure that all the prerequisites exist in the PATH.
* Make sure that PKG_CONFIG_PATH includes C:\Maliit\bin\pkgconfig (to find maliit-framework)
  Use the following arguments to qmake:
  CONFIG+=notests PREFIX=C:/Maliit LIBDIR=C:/Maliit/bin
* Do qmake, make, make install

###Testing

After having successfully built and installed both maliit-framework and plugins, you should now be able to run the provided example applications from C:\Maliit\bin, assuming the Qt libraries you built against are available in PATH:

{% highlight bash %}
cd C:\Maliit\bin
maliit-exampleapp-plainqt.exe
maliit-keyboard-viewer.exe
{% endhighlight %}

## Official packages

Note: Packaging is ongoing work.

###Ubuntu

The Maliit Input Methods are not yet in any official Ubuntu repository. However, the packages are available through Launchpad. Daily builds of Maliit packages are in the maliit-team launchpad PPA.

To install the packages, you will need to add the maliit-team's PPA to your system's software sources. Detailed instructions on how to correctly add the PPA to your current Ubuntu distribution can be found on the maliit-team daily PPA Launchpad page under the "Adding this PPA to your system" section.

After addition and repository update, proceed with installation:

{% highlight bash %}
sudo apt-get install maliit-framework maliit-plugins
{% endhighlight %}

Or use any other graphical Ubuntu package installer to install the maliit-framework and maliit-plugins packages.

Proceed to Documentation/Running

###Fedora

Maliit packages are provided using Open Build Service (OBS) in project M17N:Maliit

To install:

* Download the appropriate .repo file from http://download.opensuse.org/repositories/M17N:/Maliit/ and save it as /etc/yum.repos.d/maliit.repo.
* Install the packages maliit-framework and "maliit-plugins with the Add/Remove Software application

Proceed to Documentation/Running

###openSUSE

Maliit packages are provided using Open Build Service (OBS) in project M17N:Maliit

To install:

* Download the appropriate files from http://download.opensuse.org/repositories/M17N:/Maliit/
* Install the packages maliit-framework and "maliit-plugins with the Add/Remove Software application

###Arch Linux
Packages (stable and git) are available in AUR

To install:

{%highlight bash %}
yaourt -S maliit-framework maliit-plugins
{% endhighlight %}
Substitute yaourt with your favorite AUR helper.

Proceed to Documentation/Running

## Unofficial / Community / Third-party packages

### Debian 5 & 6
You might be able to use the packages above. Let us know to which extend you succeed with this.

### Meego
Covered on http://wiki.meego.com/Maliit/Installing

### Maemo 5 (Fremantle)
This is a rough tech demo and as such, not that useful. Note: built in legacy-mode

* Enable the Maemo's extras-devel repo (WARNING: On your own risk, can brick your device)
* Install meego-keyboard-quick (needs extras-devel),
* Install meego-im-demos

Proceed to Documentation/Running
