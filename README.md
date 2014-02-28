# Splitting Atoms

a community-built guide to hacking on the [Atom](https://atom.io) editor

> A hackable text editor for the 21st Century

> At GitHub, we're building the text editor we've always wanted. A tool you
> can customize to do anything, but also use productively on the first day
> without ever touching a config file. Atom is modern, approachable, and
> hackable to the core. We can't wait to see what you build with it.

To find out more about Atom from the team itself, read
[Introducing Atom](http://blog.atom.io/2014/02/26/introducing-atom.html) and
[The Nucleus of Atom](http://blog.atom.io/2014/02/26/the-nucleus-of-atom.html).

## Getting Started

You can start by going through
[the official Atom documentation](https://atom.io/docs) which contains a
handful of helpful guides for creating packages and themes as well as
advanced topics such as configuring your environment.

Check out the [Atom API](http://atom.io/docs/api) for more detailed
documentation on the APIs that are available to those developing packages or
hacking on existing ones.

## Packages

### Installing Packages

There are two main approaches to installing packages. You can easily do it
from inside Atom from the Package management tab in settings. For those still
inclined to using the command-line, the Atom Package Manager binary, `apm`, can
also be used to install packages as well.

#### Installing from Atom



#### Installing with apm


### Searching for Packages


### Managing Packages

Atom gives you insight into the load-time that each package is adding to the
overall performance of the editor. Based on this information, you can browse
your packages enabling and disabling them as you see fit.

#### Where are packages stored?

All the Atom configuration files, styles, packages, etc. are stored in an
Atom dot directory, namely `~/.atom`. Inside that directory, you can find
another directory named `packages` which contains all of your packages. For
those that have used NPM or Bower, it is similar to your `node_components` or
`bower_components` directories.

### Uninstalling Packages
