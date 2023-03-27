---
title: Installing
layout: page
---

If you just want to install Maliit, you will probably want to use a prebuilt package for your system.

Maliit is available in the following major Linux distributions:

* Ubuntu 22.10: `maliit-framework maliit-keyboard`
* Fedora 36, 37, 38: `maliit-framework maliit-keyboard`
* openSUSE Tumbleweed via M17N repo: `maliit-framework maliit-keyboard2`
* Arch Linux: `maliit-framework maliit-keyboard`

## Build Dependencies

openSUSE:
```bash
sudo zypper install git cmake gcc wayland-protocols-devel doxygen 'cmake(Qt5Gui)' 'cmake(Qt5Quick)' 'cmake(Qt5DBus)' 'cmake(Qt5WaylandClient)' 'cmake(Qt5XkbCommonSupport)' 'cmake(Qt5QuickControls2)' 'cmake(Qt5Multimedia)' 'cmake(Qt5Feedback)' libqt5-qtwayland-private-headers-devel anthy-devel libpinyin-devel libchewing-devel libpresage-devel hunspell-devel glib2-tools
```

## Building from source

### In the host root

The easiest way to build and install maliit from source is by installing it as root.
Make sure you don't have maliit installed via a package from your package manager.

```bash
git clone https://github.com/maliit/framework.git
git clone https://github.com/maliit/keyboard.git

cd framework/
cmake -B build/ -D CMAKE_INSTALL_PREFIX=/usr
cmake --build build/
sudo cmake --install build/
```

Remember to set `CMAKE_INSTALL_PREFIX`. This way, when you attempt to compile the keyboard component, it will automatically pick the framework build as a dependency.

```bash
cd ../
cd keyboard/
cmake -B build/ -D CMAKE_INSTALL_PREFIX=/usr
cmake --build build/
sudo cmake --install build/
```

If your system is not based on GTK, for instance Plasma, `glib-compile-schemas` might not run automatically. In this case you will need to run it manually:

```bash
cd /usr/share/glib-2.0/schemas
sudo glib-compile-schemas .
```

### In the home folder

Alternatively, you may want to install maliit in your home for local development, especially if you are in a restricted environment where you cannot install files to your host root (e.g. immutable distributions).

This method requires some additional tasks for it to work.

```bash
git clone https://github.com/maliit/framework.git
git clone https://github.com/maliit/keyboard.git

cd framework/
cmake -B build/ -D CMAKE_INSTALL_PREFIX=$HOME/maliit/usr
cmake --build build/
cmake --install build/

cd ../
cd keyboard/
cmake -B build/ -D CMAKE_INSTALL_PREFIX=$HOME/maliit/usr
cmake --build build/
cmake --install build/

cd $HOME/maliit/usr/share/glib-2.0/schemas/
glib-compile-schemas .
```

You'll need to edit `$HOME/maliit/usr/share/applications/com.github.maliit.keyboard.desktop` and change the `Exec=` line to contain the following in order for maliit to find its libraries:

```ini
Exec=LD_LIBRARY_PATH=$HOME/maliit/usr/lib64/ maliit-keyboard
```

And you will need to append `$HOME/maliit/usr/share/` to the system's `XDG_DATA_DIRS` environment variable so that your environment is able to find the keyboard. The easiest way to achieve this is by creating a file called `/etc/profile.d/maliit.sh` with the following contents:

```bash
#!/usr/bin/env sh
export XDG_DATA_DIRS=/home/yourusername/maliit/usr/share:$XDG_DATA_DIRS
```
