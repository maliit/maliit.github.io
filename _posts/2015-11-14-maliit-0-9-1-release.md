---
layout: post
title: Maliit 0.9.1 Release
date: 2015-11-14 14:14
categories: release
---

A new Maliit release was overdue. With this release a lot of smaller changes happened and a lot of bugs got fixed.

Some of the bigger changes are:

* We provide a Qt 5 input context in maliit-framework now.
* The Nemo keyboard plugin uses the Glacier-UI graphics now.
* The Gtk+ support was updated to use GDBus instead of dbus-glib.

## Where can I get it?

* framework:
  [maliit-framework-0.99.1.tar.bz2](/download/maliit-framework-0.99.1.tar.bz2) [md5](/download/maliit-framework-0.99.1.md5)
* plugins:
  [maliit-plugins-0.99.1.tar.bz2](/download/maliit-plugins-0.99.1.tar.bz2) [md5](/download/maliit-plugins-0.99.1.md5)
* inputcontext-gtk:
  [maliit-inputcontext-gtk-0.99.1.tar.bz2](/download/maliit-inputcontext-gtk-0.99.1.tar.bz2) [md5](maliit-inputcontext-gtk-0.99.1.md5)

## What is it?

Maliit provides a flexible and cross-platform input method framework. It has a
plugin-based client-server architecture where applications act as clients and
communicate with the Maliit server via input context plugins. Maliit is an open
source framework (LGPL 2) with open source plugins (BSD).

Visit [maliit.github.io](/) for more informattion about the project.

## Who contributed to this release?

* Aaron Kennedy
* Aleksi Suomalainen
* Gianni Valdambrini
* Gunnar Sletta
* Hyung Song
* Jan Arne Petersen
* Krzesimir Nowak
* Martin T. H. Sandsmark
* Michael Hasselmann
* Michael Sheldon
* Mike Sheldon
* Pekka Vuorela
* Sami Kananoja
* William Hua

## What changed in detail?

### Changes in framework since 0.99.0
* Introduced Qt5 input context, replacing the one provided by Qt. Can
  be enabled by CONFIG+=qt5-inputcontext
* Move maliit-glib from GTK+ input context package back into frameowrk
* Use GDBus in maliit-glib
* Allow plugin window reactive area and input method area reported to
  application differ
* Fix window state to have transient hint and window type as with
  Maliit 0.8x
* Made the dependency from xcb optional
* Added a CONFIG option to disable the hardware keyboard

### Changes in plugins since 0.99.0
* New plugin settings:
  - auto_repeat_behaviour: A tuple of integers, comma-separated, controlling
    delay and interval of pressed-down keys.
* Switch Nemo keyboard to Glacier-UI graphics
* Add support for extra small key widths to maliit-keyboard
* Add support for arrow icons in maliit-keyboard

### Changes in inputcontext-gtk since 0.99.0
* Move maliit-glib back to maliit-framework
* Fail gracefully without running maliit server
* Make X11 support conditionally

### Bug Fixes
* Clear preedit state on input context reset
* Reshow virtual keyboard when hardware keyboard disappears
* Fix bugs with Qt 5.3, Qt 5.4 and Qt 5.5


