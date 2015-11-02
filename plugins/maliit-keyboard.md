---
layout: page
title: Maliit Keyboard
---

## Features

__Old information from [maliit.org](https://web.archive.org/web/20131015094137/https://wiki.maliit.org/Plugins) Needs to be updated.__

This is the current status of the Maliit Keyboard and the Nemo Keyboard, compared to the MeeGo Keyboard. See the Roadmap for plans to improve the Maliit Keyboard.

 Item   |      Maliit Keyboard    |     MeeGo Keyboard   |      Nemo Keyboard 
--------|-------------------------|----------------------|--------------------
Theming | Flexible theming via INI files (key-value pairs) and graphical assets | Flexible theming via CSS and SVG | Can change assets, QML easy to change. 
Rotation | Yes | Yes | Yes
Performance | Very good | Very good | Decent (expected to improve vastly once ported to Qt 5 + QML2) 
Implementation | C++, XML | C++, XML | QML, Javascript
Haptics | No | Tactile and auditory (requires extra backend plugin[^1]) | No
Word correction/prediction | WIP, merge request available. Free engines are available and have been successfully tested (presage, hunspell). No plugin infrastructure for word engines. | Both (requires extra backend plugin) | No
Language support | Reuses language layouts of Meego Keyboard | Majority of western languages. Arabic, Hebrew and Thai. Chinese Pinyin, Zhuyin and Canjie (requires extra backend plugins[^1]). |  Layouts extensible through XML.	En, Ru
Accented characters input | Yes. Using extended key popup, or compose keys | Yes. Using extended key popup, or compose keys | No
Symbol input | Dedicated layout (via a 123/ABC/etc mode-switch button). No temporary symbol view yet. | Dedicated layout (via a 123/ABC/etc mode-switch button) and temporary symbol view (press and slide to extra symbol) | Dedicated layout (via 123/ABC/etc mode-switch button).
Content type context sensitivity[^2] | None | Number, Phone Number, Email, URL layouts | None
Application-controlled attribute extensions[^2] | No | Toolbar, Action Key Overrides | Action Key Overrides
Multitouch | No | Yes. Used to enhance the typing speed and for entering uppercase letters. | No
Hardware keyboard integration | None | On-screen symbol view | None
Additional dependencies	| Planned: presage (optional), hunspell (optional) | libmeegotouch (required), meegotouch-inputmethodengines (required), meegotouch-inputmethodreactionmaps (optional) | QtQuick

[^1]: No open source plugins available.
[^2]: Depends on Maliit's toolkit support.

