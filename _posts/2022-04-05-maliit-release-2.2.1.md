---
layout: post
title: Maliit 2.2.2 Release
date: 2022-04-05 19:02
categories: release news
---

## Maliit framework

- Re-show the keyboard on Wayland surrounding text changes

## Maliit keyboard

- Remove the legacy CC-BY 3.0 licensed artwork.
- Simplify ActionsToolbar by removing need for states
- Visual spacing improvements for Keyboard and WordRibbon
- Add a visible separator between word suggestions
- Select a minimum width for word suggestion labels
- Make word suggestion font size proportional to WordRibbon height
- Hide WordRibbon when in cursor mode
- Make wordRibbon height proportional to Keyboard keys
- Only load emoji keyboard QML when state is EMOJI
- Fix typo in internal API (@sunweaver)
- Adjust glib deprecation fix to work with glib < 2.68
- Update Italian translation
- Ensure all icon names are corrrect and using symbolic variants
- Fix some typos in QML imports
- Make sursor mode available for Japanese plugin
- Enable use of anthy-unicode instead of anthy

## Where can I get it?

* framework:
  [maliit-framework-2.2.1.tar.gz](https://github.com/maliit/framework/archive/refs/tags/2.2.1.tar.gz)
* keyboard:
  [maliit-keyboard-2.2.1.tar.gz](https://github.com/maliit/keyboard/archive/refs/tags/2.2.1.tar.gz)

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
