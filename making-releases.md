---
layout: page
title: Making Releases
---

__Old information from [maliit.org](https://web.archive.org/web/20120719215108/https://wiki.maliit.org/Development/Making_Releases) Needs to be updated.__

Before you start, make sure you have access to the infrastructure. This is needed to be able to make releases


* __0. Check that the Buildbot is green, indicating that we are ready for release__
* __1. Update the NEWS file__
  * NEWS template:
{% highlight html %}
x.y.z
=====

CHANGES SINCE $last_release
* List changes

BUG FIXES
* Fixes: MALIIT#11 …
* Fixes: BMC#12345 …
* Fixes: NB#54321 …
{% endhighlight %}

To list all commits since the last release you can do:
{% highlight bash %}
git log $last_release..HEAD
{% endhighlight %}
For the list of fixes you can use something like:
{% highlight bash %}
git log $last_release..HEAD --pretty=format:"* %s" --grep=Fixes
{% endhighlight %}
See man git-log for more options.

* __2. For framework and plugins, bump version numbers in VERSION file__
  * git commit message:
{% highlight bash %}
Changes: Bump version to y.x
{% endhighlight %}
For normal releases, just bump the package version
{% highlight bash %}
$ echo y.x > VERSION
{% endhighlight %}
For major releases/interface breaks, the following would need to be updated. These are very rare.

  * MALIIT_INTERFACE_VERSION: libmaliit (application) interface version
  * MALIIT_PLUGINS_INTERFACE_VERSION: C++ plugins interface version
  * MALIIT_PLUGINS_QUICK_INTERFACE_VERSION: Qt Quick/QML plugins interface version

* __3. Create the tarballs__
{% highlight bash %}
$ qmake && make dist
{% endhighlight %}
* __4. No-op__
* __5. Upload tarballs and .md5 files to http://maliit.org/releases/maliit-framework/ and http://maliit.org/releases/maliit-plugins/__
* __6. Upload documentation to http://maliit.org/doc/framework/latest and http://maliit.org/doc/plugins/latest__
* __7. Update packages in M17N:Maliit OBS__
{% highlight bash %}
python obs-update-version M17N:Maliit maliit-framework x.y.z \
maliit-framework-x.y.z.tar.bz2 "Jon Nordby <jonn@openismus.com>"    
python obs-update-version M17N:Maliit maliit-plugins z.y.z \
maliit-plugins-x.y.z.tar.bz2 "Jon Nordby <jonn@openismus.com>"
{% endhighlight %}
This script is found in the maliit-buildbot-configuration repository, and requires osc.

To do the steps manually use either the web interface or the "osc" commandline client.

  * Upload new source tarballs
  * Update version number in package-name.spec
  * Reset release version number to 0 in package-name.spec
  * Add changelog entry to package-name.spec: Updated to upstream version x.y.z
See http://en.opensuse.org/Portal:Packaging for documentation on OBS.

* __8. Create (signed) git tag__
{% highlight bash %}
$ git tag -s -m "Released version x.y.z - ${insertWittyReleaseNameHere}" x.y.z
{% endhighlight %}
Witty release names are only requires for bigger version jumps (x or y changes), not for minor releases (z or smaller changes).

* __9. Push the tag to master. Warning: Make sure the tag is correct first!__
{% highlight bash %}
$ git push origin HEAD:master # The commits
$ git push origin x.y.z # The tag
{% endhighlight %}
* Keep in mind that a git tag is tied to a specific commit id. If you rebase your branch, then the commit id's will most likely change, meaning that your git tag will point to an old commit id. You will have to delete the tag and create a new one, in that case.

* __10. Update the 'latest' branches to point to the new tags.__

{% highlight bash %}
$ git push origin master:latest
{% endhighlight %}

* __11. Update the Maliit recipes in Launchpad__

{% highlight bash %}
python lp-update-version.py maliit maliit-plugins z.y.x
python lp-update-version.py maliit maliit-framework z.y.x
{% endhighlight %}
This script is found in the maliit-buildbot-configuration repository, and requires launchpadlib.

To do the same manually, go through every single recipe and, update the upstream version number in the "Recipe Contents" (bottom of page).

* __12. Write the release notes (see template below) and send them to the appropriate mailing lists.__

Always send the announcement to maliit-discuss and maliit-announce. Include non-Maliit lists only if there is a significant change relevant for the subscribers of that list.

* __13. Update the list of releases.__

Release notes template

Use the template below to write release notes.
{% highlight html %}

What's new?
===========

Write about an interesting aspect for this release. Also give hints if
changes might affect packaging, and give packaging advice if appropriate.

Where can I get it?
===================

* framework:
  http://maliit.org/releases/maliit-framework/maliit-framework-x.y.z.tar.bz2
* plugins:
  http://maliit.org/releases/maliit-plugins/maliit-plugins-x.y.z.tar.bz2

What is it?
===========

Maliit provides a flexible and cross-platform input method framework. It has a
plugin-based client-server architecture where applications act as clients and
communicate with the Maliit server via input context plugins. Maliit is an open
source framework (LGPL 2) with open source plugins (BSD).

Visit http://maliit.org for more informattion about the project.

Who contributed to this release?
================================

* List authors of this release
  $ git log $last_release..HEAD 0.80.5.. --pretty="format:* %aN" | sort | uniq

What changed in detail?
=======================

CHANGES IN FRAMEWORK SINCE x.y
* List the details from the framework's NEWS file.

CHANGES IN PLUGINS SINCE x.y
* List the details from the plugins' NEWS file.

BUG FIXES
* List all bug fixes of framework and plugins.
{% endhighlight %}
