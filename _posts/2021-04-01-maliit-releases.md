---
layout: post
title: Maliit Framework 1.0.0 and Maliit Keyboard 2.0.0 Releases
date: 2021-04-01 14:00
categories: release
---

No April Fool's joke: Today we're releasing Maliit Framework 1.0.0 and Maliit Keyboard 2.0.0.

## Maliit Framework 1.0

Not much has happened since our 0.99.2 release. [Marius Gripsgard](https://github.com/mariogrip)
and [Andrés B.S.](https://github.com/surprized) fixed a few things around pkgconfig.
At the stable state Maliit is, we think it's fair to assume that the next big change
will be the eventual port from Qt 5 to Qt 6 (not that we mind getting suprised with
pull requests adding features before that), so let's just call the current state 1.0.0.

## Maliit Keyboard 2.0.0

This release is a bit more exciting. Our last Keyboard release was 0.99.1 as part
of the maliit-plugins bundle way back in 2015.
Then Canonical came and forked the source code to build a virtual keyboard for
Ubuntu Touch, made some improvements, and then went away again because they
discontinued Ubuntu Touch. Nevertheless, their work was valuable enough to use
it as base for further improvements and bringing the code back into the Maliit fold.
From 2017 until somewhat recently, [Jan Arne](https://github.com/jpetersen) worked pretty
much by himself on improvements such as removing deprecated Ubuntu Touch dependencies,
porting the code from QMake to CMake, and so on. More recently the good folks at KDE
looked for a new on-screen keyboard, though, and send in a few pull requests.
Overall, the amount of changes justifies the jump directly to 2.0.

With KDE and their Plasma project moving to Maliit, Linux distributions want proper
releases of dependencies as well, so here it is.

## Where can I get it?

* framework:
  [maliit-framework-1.0.0.tar.bz2](/download/maliit-framework-1.0.0.tar.bz2)
* keyboard:
  [maliit-plugins-2.0.0.tar.bz2](/download/maliit-keyboard-2.0.0.tar.bz2)

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
