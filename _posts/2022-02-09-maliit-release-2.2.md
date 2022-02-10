---
layout: post
title: Maliit 2.2.0 Release
date: 2022-02-09 20:00
categories: release news
---

## Maliit framework

- Fix sending of modifiers and keysyms on Wayland
- Fix Qt and glib deprecation warnings
- Update the Doxyfile
- Use text-input-unstable-v2 protocol
- Enable GitHub Actions CI and fix tests
- Fix build failure when XCB is disabled
- Lower CMake requirement to 3.5


## Maliit keyboard

- Revert to simpler method of word engine plugin loading
- Improved layout switching behavior to cycle through all enabled languages
- Handle invalid values being set for active and enabled languages
- Remove previous-language setting
- Support for disabling keyboard hide and unhide animations
- Integrate emoji layout into main keyboard
- Fix the default hunspell dictionary path
- Fix Qt and glib deprecation warnings during compilation
- Add ẞ and missing currency symbols to German keyboard
- Fix build with hunspell disabled
- Synchronize changes from Lomiri keyboard fork
  - Selection mode available when in cursor mode now
  - Toolbar in cursor mode for undo/redo/select all and cut/copy/paste
  - Belarusian layout
  - Bulgarian layout
  - English (Dvorak) layout
  - French (Swiss) layout
  - Lithuanian layout
  - Macedonian layout
  - Thai layout
  - Turkish layout
- Fix compilation with presage enabled on c++17 default compilers
- Enable translations support
- Set haptic feedback duration to 100ms and intensity to 0.5
- Add haptic feedback to spacebar
- Use the correct kcm name for settings in Plasma Mobile


## Where can I get it?

* framework:
  [maliit-framework-2.2.0.tar.gz](https://github.com/maliit/framework/archive/refs/tags/2.2.0.tar.gz)
* keyboard:
  [maliit-keyboard-2.2.0.tar.gz](https://github.com/maliit/keyboard/archive/refs/tags/2.2.0.tar.gz)

## What is it?

Maliit provides a flexible and cross-platform input method framework. It has a
plugin-based client-server architecture where applications act as clients and
communicate with the Maliit server via input context plugins. Maliit is an open
source framework (LGPL 2.1 or later) and an open source on-screen keyboard (LGPL 3.0 only).

Maliit is being used by [KDE for Plasma](https://blog.martin-graesslin.com/blog/2021/03/using-maliit-keyboard-in-a-plasma-wayland-session/),
[LG for webOS](https://github.com/webosose/maliit-framework-webos),
[Ubuntu Touch](https://gitlab.com/ubports/core/lomiri-keyboard),
[LuneOS](https://github.com/webOS-ports/webos-keyboard),
[Sailfish OS](https://git.sailfishos.org/mer-core/maliit-framework),
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
