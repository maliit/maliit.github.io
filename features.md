---
layout: headerpage
title: Features
---

__Old page from [maliit.org](https://web.archive.org/web/20120217190655/https://wiki.maliit.org/Features) Needs to be updated.__

## For integrators and developers
 * Input Methods can be implemented as plugins
 * A number of [input method plugins](/plugins/) are available
 * Error correction/prediction engines can be implemented as plugins
 * Framework is licensed LGPL
 * [MeeGo Keyboard](/plugins/meego-keyboard/) has theming abilities via CSS file
 * [MeeGo Keyboard](/plugins/meego-keyboard/) has customizable layout files
 * [MeeGo Keyboard](/plugins/meego-keyboard/) has full hardware keyboard integration. The Maliit Keyboard supports the Nokia N950's hardware keyboard (but only cycle keys and long press). TODO: Clarify Maliit Keyboard hardware support.
 * MeeGo Feedback framework has swappable backends (for haptics, etc.)
 * Support for additional toolkits can be implemented by using the DBus connection for the Input Context

##For end users
Following are the high level end-user features supported by Maliit:

 * Multitouch virtual keyboard ([MeeGo Keyboard](/plugins/meego-keyboard/))
 * Landscape and portrait QWERTY with dedicated symbol views ([MeeGo Keyboard](/plugins/meego-keyboard/), [Maliit Keyboard](/plugins/maliit-keyboard/))
 * Support for multiple languages and scripts (e.g. latin, cyrillic, arabic, chinese) ([MeeGo Keyboard](/plugins/meego-keyboard/))
   * See current layouts at MeeGo gitorious
 * Number/phone number layouts for entering numbers/phone numbers ([MeeGo Keyboard](/plugins/meego-keyboard/))
 * Context sensitive and dynamic action key ([MeeGo Keyboard](/plugins/meego-keyboard/), [Maliit Keyboard](/plugins/maliit-keyboard/))
   * e.g. replacing enter icon with search icon and highlighting the key in search fields - and respective search key inactive when search field empty
 * Context sensitive layouts ([MeeGo Keyboard](/plugins/meego-keyboard/))
   * e.g. replacing ',' key with '@' in e-mail address fields
 * Simple interactions (as defined in MeeGo Basics) ([MeeGo Keyboard](/plugins/meego-keyboard/), [Maliit Keyboard](/plugins/maliit-keyboard/))
   * Swipe sideways to easily switch between different active keyboard layouts and other input methods
   * Swipe down to close virtual keyboard or alternatively tap outside the active input area to close keyboard
 * Low-latency haptics typing feedback (with feedback framework backend); sound,tactile ([MeeGo Keyboard](/plugins/meego-keyboard/))

![Virtual keyboard interaction: opening and closing the keyboard](/images/text-input-1.png)

 * Cut/Copy/Paste for text input (libmeegotouch, Qt Components)
   * Separate text editor widget for text input fields
 * Error correction / word prediction for virtual keyboard (with error correction / prediction engine) ([MeeGo Keyboard](/plugins/meego-keyboard/))
   * Separate widget for correction/prediction candidates ([MeeGo Keyboard](/plugins/meego-keyboard/))
 * Hardware keyboard (MeeGo Keyboard)
   * Long pressing of keys either to autorepeat (e.g. arrow keys, backspace) or to input secondary characters (e.g. numbers, symbols)
   * Possibility to extend hardware keys with virtual keys (e.g. for additional symbols)

![Text input with hardware keyboard](/images/text-input-2a.png)

 * Toolbar for application-specific input content ([MeeGo Keyboard](/plugins/meego-keyboard/))
   * For placing buttons, labels etc.
   * Toolbar located on top of virtual keyboard, with hardware keyboard in the bottom of the screen
   
![Placing application specific actions in the input toolbar, when application UI is not visible or "Enter" action is not adequate](/images/confirming.png)

 * External input methods
   * e.g. Bluetooth keyboards
