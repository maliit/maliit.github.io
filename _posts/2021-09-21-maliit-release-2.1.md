---
layout: post
title: Maliit 2.1.0 Release
date: 2021-09-21 14:00
categories: release news
---

## Maliit framework

- Fix usage of zwp_input_method_v1::content_purpose_digits
- Update input method area when activation is lost
- Load compose inputcontext plugin for physical keyboarad handling
- Stop client crashing when QGuiApplication::focusObject is null
- Clean up FindGIO.cmake to allow working with older cmake.
- Only allow focus removal from input items.
- Ensure orientation updates are always sent when valid
- Fix the broken tests build.
- Show the panel as the keyboard interface is reset
- Fix search for qtwaylandscanner on 32-bit architectures
- Do not build examples by default
- Add cmake option to build examples

## Maliit keyboard

- Remove label from language key on emoji keyboard
- Remove the unused and outdated styling support
- Support icon themes to load the icons
- Make sure Settings also work when running on Plasma
- left/right arrow keypress: Don't check for surrounding text
- Bypass argument count problem for newPredictionSuggestions and newSpellingSuggestions
- Clean up unused code
- Let language features customize primary candidate index
- Recalculate primary candidates after refreshing candidate list
- Process pinyin sequence properly
- Handle partial candidate words in pinyin properly
- Allow force refreshing candidate list
- Allow delaying committing text when a candidate word is selected
- Provide appstream information
- Use Q_ENUM
- Optimise symbols for Simplified Chinese
- Use only valid pinyin symbols on pinyin keyboard
- Fix incorrect key name in tablet.json
- Don't crash when no language plugin is loaded

## Where can I get it?

* framework:
  [maliit-framework-2.1.0.tar.gz](https://github.com/maliit/framework/archive/refs/tags/2.1.0.tar.gz)
* keyboard:
  [maliit-keyboard-2.1.0.tar.gz](https://github.com/maliit/keyboard/archive/refs/tags/2.1.0.tar.gz)

## What is it?

Maliit provides a flexible and cross-platform input method framework. It has a
plugin-based client-server architecture where applications act as clients and
communicate with the Maliit server via input context plugins. Maliit is an open
source framework (LGPL 2.1 or later) and an open source on-screen keyboard (LGPL 3.0 only).

Maliit is being used by [KDE for Plasma](https://blog.martin-graesslin.com/blog/2021/03/using-maliit-keyboard-in-a-plasma-wayland-session/),
[LG for webOS](https://github.com/webosose/maliit-framework-webos),
[UBPorts](https://github.com/ubports/keyboard-component),
[LuneOS](https://github.com/webOS-ports/webos-keyboard),
[Sailfish OS](https://git.sailfishos.org/mer-core/maliit-framework),
and likely others.

Visit [maliit.github.io](/) for more information about the project.

## Call for contributions

Maliit's website could benefit from a little love. Some of the information is
no longer up to date.
If anybody out there has some time to spare to fix it up a little bit, hop to
https://github.com/maliit/maliit.github.io and send us a pull request.

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

