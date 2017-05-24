---
layout: post
title: Standalone Mode and updated Wayland support
date: 2017-05-24 21:23
categories: news
---

There is a new standalone mode added to Maliit, which allows to just include the server into the plugin. Instead
of having to run maliit-server and loading a keyboard implementation as a plugin one can just create a standalone
executable (in addition). That is already done for the new [Maliit Keyboard 2](/news/2017/05/24/maliit-keyboard/)
where a maliit-keyboard executable is created which can just be run with the Maliit DBus or the the Wayland input
method protocol.

In addition we [updated the Wayland support](https://github.com/maliit/framework/commit/22be135155ff772c098432275d776d6696b54a00)
in maliit-framework to use the `zwp_input_method_v1` protocol used in weston currently. We also added a
[Qt wayland-shell-integration plugin](https://github.com/maliit/framework/commit/06367f157f6686a49ea350a64c1691c18e9c1d01)
for the input panel.

With a maliit-keyboard.sh script like

    #!/bin/sh
    export QT_WAYLAND_SHELL_INTEGRATION=inputpanel-shell
    maliit-keyboard -platform wayland

one can just use

    [input-method]
    path=/usr/bin/maliit-keyboard.sh

to run maliit-keyboard inside weston again.
