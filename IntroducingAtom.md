---
layout: page
title: Introducing Atom
---

An introduction to Atom and the things you need to know before you start developing.

## Getting Started with Packages

### Installing Packages

There are two main approaches to installing packages. You can easily do it
from inside Atom from the Package management tab in settings. For those still
inclined to using the command-line, the Atom Package Manager binary, `apm`, can
also be used to install packages as well. This utilises the Node Package
Manager, `npm`, behind the scenes.

#### Installing from Atom

From the Atom editor menus, navigate to *Atom* -> *Preferences*.

From there, open the *Packages* tab and have at it.

The other way to get to this menu is to take advantage of command palette.
Press `Cmd-shift-P` to bring up the command palette and then start typing,
*packages*. You should see the *Settings View: Install Packages* option show
up in the palette.

#### Installing with apm

On the command line, type `apm install package-name`.

### Searching for Packages

You can search for packages from *Atom* -> *Preferences* -> *Packages*,
on [the main Atom site](http://atom.io/packages), or from `apm`.
To search for packages on `apm`, type `apm search package-name` in the command
line. One thing to keep in mind when searching for packages is that some
package authors prefix their Atom packages with *atom-*package-name, others
don't. There doesn't seem to be a consistent standard, so it's probably best to
leave the *atom-* prefix off your search, unless you know the package you're
looking for starts with it.

### Managing Packages

Atom gives you insight into the load-time that each package is adding to the
overall performance of the editor. Based on this information, you can browse
your packages enabling and disabling them as you see fit.

#### Where are packages stored?

All the Atom configuration files, styles, packages, etc. are stored in an
Atom dot directory, namely `~/.atom`. Inside that directory, you can find
another directory named `packages` which contains all of your packages. For
those that have used NPM or Bower, it is similar to your `node_modules` or
`bower_components` directories.

### Uninstalling Packages

Atom uses a clone of `npm` called `apm` as it's package manager. (See [list of `apm` command](https://github.com/jbranchaud/splitting-atoms/blob/master/Apm.md).)

You can see all installed non-bundled packages by going to the Packages section on left hand side of the Settings view (`cmd-,`) or by using the comman `apm list`.

#### Uninstall a package using `apm`

To uninstall a package using `apm`, simply run the command `apm uninstall <package name>`. This will remove tha package from your `~/.atom/packages/` directory.

Here's a sample run of the command:

    $ apm uninstall toggle-quotes
    Uninstalling toggle-quotes ✓

#### Uninstall a package using Atom

All third-party packages can also be uninstalled from within Atom. Simply go to Settings (`cmd-,`). In the settings sidebar, click on a package you want to uninstall and simply click on the "Uninstall" button. This will remove tha package from your `~/.atom/packages/` directory and take you to the main packages page.

## More About Atom

You can start by going through
[the official Atom documentation](https://atom.io/docs) which contains a
handful of helpful guides for creating packages and themes as well as
advanced topics such as configuring your environment.

Check out the [Atom API](http://atom.io/docs/api) for more detailed
documentation on the APIs that are available to those developing packages or
hacking on existing ones.