---
title: Packaging Guidelines
layout: page
---

__Old information from [maliit.org](https://web.archive.org/web/20120121185002/https://wiki.maliit.org/PackagingGuidelines) Needs to be updated__

__Status: Draft__

Maliit currently consists of two repositories, maliit-framework and maliit-plugins. These two repositories contains several different components, that distributions might want to split up. Here is a guideline.

## maliit-framework

Core libraries of Maliit. Package name: maliit-framework.

When packaging, some actions "make install" does by default will need to be deactivated, and the actions done in post- install/uninstall instead. Currently this includes gconf schema registration and GTK+ immodule cache update. Use "qmake HELP=1" for information on how to do this.

Subpackages are divided into three groups depending based on what should happen when the top-level package "maliit-framework" is installed by the user.

* Core: MUST be installed
* Toolkit support: SHOULD be installed
* Extra: MAY be installed

All libraries are versioned and parallel installable. For that reason binary packages MUST also be versioned.

Core

* Common files/library code - Used by both application, server and plugin interfaces
  * Package name: maliit-framework
  * post install/uninstall MUST register gconf schemas (distro specific)
  * Optional: -dev package
  * Files
    * /usr/include/maliit/framework-*/maliit/*.h
    * /usr/lib/pkgconfig/maliit-framework-*.pc
    * $GCONF_DATADIR/.../maliit-framework.schemas
* Maliit Server - The Maliit server/service
  * Package name: maliit-server
  * Files
    * /usr/bin/maliit-server
* C++ Plugin Interface - Interfaces for Maliit Input Method Plugins
  * Package name: libmaliit-plugins0
  * Optional: -dev package
  * Files
    * /usr/include/maliit-plugins*/*.h
    * /usr/lib/libmaliit-plugins*.so*
    * /usr/lib/pkgconfig/maliit-plugins*.pc
* Qt Quick Plugin Interface - Interfaces for QML-based Maliit Input Method Plugins
  * Package name: libmaliit-plugins-quick0
  * Optional: -dev package
  * Files
    * /usr/include/maliit/plugins-quick*/*.h
    * /usr/lib/libmaliit-plugins-quick*.so*
    * /usr/lib/pkgconfig/maliit-plugins-quick*.pc

Toolkit support

* Qt Input Context - Qt plugin for basic Qt 4 toolkit support
  * Package name: maliit-inputcontext-qt4
  * Files
    * $QT4_LIBDIR/plugins/inputmethods/libmaliit.so
* GTK+ Input Context - GTK+ plugin for basic GTK+ toolkit support
  * Package name: maliit-inputcontext-gtk2 and maliit-inputcontext-gtk3
  * Additional dependencies: GTK2 and GTK3
  * post install/uninstall MUST update the GTK+ immodule caches (distro specific)
  * Files
    * $GTK2_LIBDIR/.../libmaliit.so
    * $GTK3_LIBDIR/.../libmaliit.so
* libmaliit - Toolkit support extension library for Qt applications
  * Package name: libmaliit1
  * Optional: -dev package
  * Files
    * /usr/lib/pkgconfig/maliit-1.0.pc
    * /usr/lib/libmaliit*.so

Extra

* Examples
  * Package name: maliit-framework-examples
  * Files
    * /usr/bin/maliit-exampleapp-*
* Documentation
  * Package name: maliit-framework-doc
  * Files
    * /usr/share/doc/maliit-framework/html
* Tests
  * Package name: maliit-framework-tests
  * Files
    * /usr/lib/maliit-framework-tests/
    * /usr/share/maliit-framework-tests/
* SDK
  * Package name: maliit-framework-sdk
  * Requires: maliit-framework-doc
  * Files
    * /usr/bin/maliit-sdk
    * /usr/share/doc/maliit-framework/maliit-sdk

## maliit-plugins

Reference Input method plugins provided by the Maliit project. Uses maliit-framework.

Packagename: maliit-plugins

An input method plugin is required for Maliit to do anything useful. This can either be one of the reference plugins or a third-party plugin. Distributions SHOULD set up a virtual package "maliit-inputmethod-plugin", that all packaged input method plugins for Maliit provides, and the "maliit-framework" package should depend on this virtual package.

Additionally the framework is needed for the input method plugin to be useful. Installing a plugin like 'maliit-keyboard' MUST pull in everything needed in the framework for it to work. This can be done by making the plugin binary package depend on the maliit-framework metapackage.

* Maliit Keyboard Core Library - Reusable core library for on-screen keyboard plugins
  * Packagename: libmaliit-keyboard
  * /usr/lib/libmaliit-keyboard.so
* Maliit Keyboard UI Library - Reusable UI library for on-screen keyboard plugins
  * Packagename: libmaliit-keyboard-view
  * /usr/lib/libmaliit-keyboard-view.so
* Maliit Keyboard Layouts - Keyboard Layout files
  * Packagename: maliit-keyboard-layouts
  * /usr/share/?
* Maliit Keyboard Themes - Theme files for Maliit Keyboard
  * Packagename: maliit-keyboard-themes
  * Note: it should be possible for downstreams and integrators to install additional themes
* Maliit Keyboard - The Maliit reference keyboard plugin
  * Packagename: maliit-keyboard
  * Depends on: libmaliit-plugins, libmaliit-keyboard-view, libmaliit-keyboard, maliit-keyboard-layouts
  * /usr/lib/maliit/plugins-0.80/libmeego-keyboard-plugin.so
* Nemo Keyboard: Pure QML input method plugin for Nemo Mobile
  * Packagename: nemo-keyboard
  * Depends on: libmaliit-plugins-quick0
  * Currently data-only (arch independent)
