---
layout: headerpage
title: Development
---

__Old information from [maliit.org](https://web.archive.org/web/20131021093510/https://wiki.maliit.org/Development) Needs to be updated.__

##Roadmap

See [Roadmap](/roadmap/). You can also propose new [ideas](/ideas/).

##Repositories

* Maliit framework:
{% highlight bash %}
git clone https://github.com/maliit/framework.git
{% endhighlight %}
* Maliit plugins (virtual keyboards etc.):
{% highlight bash %}
git clone https://github.com/maliit/plugins.git
{% endhighlight %}
For how to build, see Documentation/Installing

##Branches

 * Qt 4:
   * stable (supports self-composition): _maliit-framework_: __0.81__, _maliit-plugins_: __0.80__
   * unstable (supports some experimental features, some Qt 5 support): _maliit-framework_/_maliit-plugins_: __0.94-qt4__
 * Qt 5
   * unstable (focus is cleanup for next stable 1.0 release series): _maliit-framework_/_maliit-plugins_: __master__
      * Both reference plugins have been ported to Qt5/QtQuick2: In both cases, the UI is done via QML.
      * Input context reaching feature parity with Qt4 one (WIP, will override the Qt5-provided input context, see [1]).
      * Still missing in Qt5: Wayland input method support, so that Maliit can be used with Wayland and Qt5 applications.

##Releases

 * Howtos: [Making Releases](/making-releases/)

###Maliit 0.99 (unstable)

 * 0.99.0: Release notes, tarballs: framework, plugins, inputcontext-qt4, inputcontext-gtk, (March 27, 2013)

### Maliit 0.90 (unstable)

 * 0.94.2: Release notes, framework tarball, plugins tarball (February 13, 2013)
 * 0.94.0: Release notes, framework tarball, plugins tarball (January 14, 2013)
 * 0.93.1: Release notes, framework tarball, plugins tarball (October 28, 2012)
 * 0.93.0: Release notes, framework tarball, plugins tarball (October 28, 2012)
 * 0.92.5.1: Release notes, framework tarball, plugins tarball (October 9, 2012)
 * 0.92.5: Release notes, framework tarball, plugins tarball (September 27, 2012)
 * 0.92.4: Release notes, framework tarball, plugins tarball (August 8, 2012)
 * 0.92.3: Release notes, framework tarball, plugins tarball (July 18, 2012)
 * 0.92.2: Release notes, framework tarball, plugins tarball (June 29, 2012)
 * 0.92.1: Release notes, framework tarball, plugins tarball (June 01, 2012)
 * 0.92.0: Release notes, framework tarball, plugins tarball (May 07, 2012)
 * 0.91.0: Release notes, framework tarball, plugins tarball (March 31, 2012)
 * 0.90.0: Release notes, framework tarball, plugins tarball (March 01, 2012)

### Maliit 0.81 (current stable)

 * 0.81.4: Release notes, framework tarball, plugins tarball (February 1, 2013)
 * 0.81.3: Release notes, framework tarball, plugins tarball (January 27, 2012)
 * 0.81.2: Release notes, framework tarball, plugins tarball (December 23, 2011)
 * 0.81.1: Release notes, framework tarball, plugins tarball (December 7, 2011)
 * 0.81.0: Release notes, framework tarball, plugins tarball (November 22, 2011)

### Maliit 0.80

 * 0.80.8: Release notes, framework tarball, plugins tarball (November 7, 2011)
 * 0.80.7: Release notes, framework tarball, plugins tarball (October 21, 2011)
 * 0.80.6: Release notes, framework tarball, plugins tarball (September 21, 2011)
 * 0.80.5: Release notes, framework tarball, plugins tarball (August 22, 2011)
 * 0.80.4: Release notes, framework tarball, plugins tarball (July 20, 2011)
 * 0.80.3: Release notes, framework tarball, plugins tarball (July 13, 2011)
 * 0.80.2: Release notes, framework tarball, plugins tarball (July 6, 2011)
 * 0.80.1: Release notes, framework tarball, plugins tarball (June 27, 2011)
 * 0.80.0: Release notes, framework tarball, plugins tarball (June 20, 2011)

##Contributing

* Want to contribute, but unsure what to do? See our Ideas page.
* Finding it hard to understand the code, or have other questions? See the Contact page for how to get in touch.

### Guidelines

#### Starting out

 * If you are working on a patch for a bug in one of the downstreams (like MeeGo), please also file a bug report there so people know what you're working on.
 * If you are implementing a new feature, it is smart to discuss it on the mailing list first.
 * When writing the patches, follow the coding style in the files you are changing. In many aspects (but not all), we follow the Qt coding conventions.

#### Merge Request

 * Before requesting a merge, make sure to run the unit tests. make check does this
Make sure that each individual commit consists of one logical change. Try to keep commits small when possible, it eases review.
 * Clone our repository on Maliit gitorious and create a merge request. We will then review your patches and give feedback. Note: even those with commit access needs to create merge requests for non-trivial changes.
   * If you do not get feedback on your merge request in a timely manner, say 1 week, feel free to prod us through one of the above mentioned communication channels.
   * We expect people to stick around to fix up issues found during patch review. If you don't, there is a high risk of your patches not getting merged.
 * When code is reviewed and accepted, it is the responsibility of the person merging that the build still works, and that the commits have review information.

#### Commit Rights
We currently do not have a concrete policy for giving out commit rights to the mainline repositories. However, it is our intention that contributors that build up a track record with the project are able to easily get commit rights. Do note that even with commit rights, above guidelines must be followed. In particular patches need to be submitted as merge requests and be properly reviewed before being merged to master branches.

#### Commit Message Guidelines
Please make sure to follow our commit message guideline. See the git log for some examples.

 * The first line should provide a short overview of your commit. Bugfixes should start with "Fixes: ", new features/functionality with "New: ", and changes with "Changes: ".
 * The second line should be empty.
 * Add a "RevBy: Name of reviewers" in the details section for the review information, or "RevBy: TrustMe" for unrevised commits. Ideally all commits are reviewed!
 * Then a details section may follow. Here you explain the problem/fix/feature in more detail, and can link to external documents that provide more information.

## Review checklist

Checklist of things to check during review.

* Commit message follows the guidelines.
* Commits are small and only contain a single logical change.
* New files have copyright headers.
* Code is const-correct.
* Code follows coding-style (TODO: document the coding-style).
* Intent is sufficiently reflected in variable, method and class names.
* Non-obvious conditionals have an explaining comment of why the logic is needed or what it does.
* New API has good documentation for each class and method.
* Where applicable, code has been generalized and factored out into separate methods or classes.
* Ask for auto tests if introduced logic appears too complex.
* ...

##Maliit in downstreams

* MeeGo: http://wiki.meego.com/Maliit
* Ubuntu: https://launchpad.net/maliit
  * Daily builds: https://launchpad.net/~maliit-team/+archive/daily
    * Add "ppa:maliit-team/daily" to Software Sources
  * Feedback thread: http://ubuntuforums.org/showthread.php?p=11447669

##Bugreports, patches and merge requests

###Maliit Upstream
Maliit bugs are tracked at bugs.maliit.org

All open bugs by component

###Maliit Downstream

This area is for keeping track of things that concern Maliit, and things done by the Maliit team in related projects.

Maliit openSUSE OBS project request
Maliit project request on freedesktop.org
Maliit bugs in Nemo Mobile

## Maliit in the news and on the web

References to Maliit from other places on the web. Also see Reviews.

 * [Slashdot: On-Screen Keyboard Maliit Demoed With Gnome 3](https://web.archive.org/web/20131021093510/http://hardware.slashdot.org/story/11/04/30/137205/On-Screen-Keyboard-Maliit-Demoed-With-Gnome-3)

Web searches. Query: maliit keyboard OR "input method" OR meego -ang

 * [Webpages](http://www.google.de/search?q=maliit+keyboard+OR+%22input+method%22+OR+meego+-ang)
 * Discussions
 * Realtime
 * Blogs
 * YouTube

## Documentation working area

Here is the working area to keep track of the status of and work on the documentation.

* Goal: Every aspect of Maliit is well-documented, and the documentation easily accessible.
* Primary focus is on consumers of Maliit: Third-party developers and integrators

###Important cases

* Creating and adding a new layout file to the keyboard
* Developing a new input method plugin
* Using Maliit in an application
* Integrating Maliit in a product
* Developing a new engine plugin
* Adding support for additional application toolkits

###Documentation status

Again roughly ordered by importance.

Item | Status | Description
---|---|---
http://wiki.maliit.org | 60% | Our public webpage/wiki page, starting point for all information about our project. In OK shape.
http://maliit.org/doc/ | 90% |Updated docs should be on found on maliit.org/doc, for every release. Both plugins and framework. Symbolic link to latest release should also exist.
__Framework__ | |
Overall architecture | 30% |Some docs exists in framework source tree, but is very outdated
Application extension API (libmaliit) | 20% | Some API docs exists. Some example applications (TODO: URLs) exist.
Toolkit support/integration | 10% | Implicitly all keyboard/IM features are available for MTF. No documentation about plain Qt, QML, Clutter or Gtk+
Input Method Plugin API | 60% | Example plugins exists, initial plugin SDK published. Need to remove the outdated tutorial from framework docs
Toolkit integration concepts | 20% | Key concepts like pre-edit injection, and widget relocation should be documented. Purpose: make it easy for others to improve toolkit integration, and to bring new people up to date. Widget relocation is documented.
Input Method/framework settings system | 0% |
Input Method Framework X11 window handling | 0% | Passthrough window, Self-compositing, plugin pixmap drawing, rotation animation.
Input Context DBus API | 0% |
__Plugins__ | |
Reference plugin features | 50% | [Features](/features/) and [Plugins](/plugins/)
Meego Keyboard theming (CSS) | 100% | Documentation in source tree and online
Meego Keyboard layouts | 100% | Documentation in source tree and online.
