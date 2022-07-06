---
layout: post
title: Maliit 2.3.0 Release
date: 2022-07-06 12:00
categories: release news
---

## Maliit framework

- Fix paths in maliit-defines.prf
- Use compose input plugin fallback only if key redirection is disabled
- Remove leftover code from Qt 4 times
- Enable installing unit tests again
- Remove legacy unused Maemo-specific code
- Use QLoggingCategory for logging
- Fix application orientation angle back to clockwise
- Add the Mir input panel window type flag
- Use CMAKE_INSTALL_FULL_* paths in pkgconfig files
- Remove the unused and unnecessary gtk3 wayland input context plugin
- Remove unused and useless install target


## Maliit keyboard

- Add CI build rule to build on KDE Neon
- Remove unused window flag setting code
- Replace remaining context properties with singletons
- Remove unused and useless install target
- Fix builds without Pinyin
- Fix the build of unit tests and enable them by default
- Fix a possible undefined error in CharKey
- Improve the PhoneNumber keyboard layout
- Fix the settings URL for Plasma Mobile kcm renaming
- Use new syntax for Connections components
- Rely on QQC2 styles insted of an internal themes implementation


## Where can I get it?

* framework:
  [maliit-framework-2.3.0.tar.gz](https://github.com/maliit/framework/archive/refs/tags/2.3.0.tar.gz)
* keyboard:
  [maliit-keyboard-2.3.0.tar.gz](https://github.com/maliit/keyboard/archive/refs/tags/2.3.0.tar.gz)

## What is it?

Maliit provides a flexible and cross-platform input method framework. It has a
plugin-based client-server architecture where applications act as clients and
communicate with the Maliit server via input context plugins. Maliit is an open
source framework (LGPL 2.1 or later) and an open source on-screen keyboard (LGPL 3.0 only).

Maliit is being used by [KDE for Plasma](https://blog.martin-graesslin.com/blog/2021/03/using-maliit-keyboard-in-a-plasma-wayland-session/),
[LG for webOS](https://github.com/webosose/maliit-framework-webos),
[Ubuntu Touch](https://gitlab.com/ubports/core/lomiri-keyboard),
[LuneOS](https://github.com/webOS-ports/webos-keyboard),
[Sailfish OS](https://github.com/sailfishos/maliit-framework),
and likely others.

Visit [maliit.github.io](/) for more information about the project.

## Call for contributions

Maliit's website could benefit from a little love. Some of the information is
no longer up to date.
If anybody out there has some time to spare to fix it up a little bit, hop to
[github.com/maliit/maliit.github.io](https://github.com/maliit/maliit.github.io) and send us a pull request.

Should anybody with some influence at Canonical happen to read this announcement:
We have nothing against the LGPL 3.0 but we'd like some consistency in our
licensing. Maliit Keyboard was originally BSD-licensed but Canonical code from 2014
until 2017 is licensed under LGPL-3.0-only. If Canonical could send us a PR
replacing the LGPL 3.0 headers with BSD ones, we'd appreciate it.

We currently lack the manpower to crawl through various forks of Maliit Framework
and Keyboard. We're aware of them and we totally support the right of anybody
to fork all Free Software code but not always is new code in those forks specific
to custom implementations. A helping hand or two that ports improvements useful
for our upstream code would, again, be very appreciated.
