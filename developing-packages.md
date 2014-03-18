---
layout: page
title: Developing Packages
---

An introduction to developing packages for Atom.

## Assigning Commands For Your Package

...

## Assigning Keybindings For Your Package

The commands that your package defines are the main interface through which users of your package will access or invoke certain features. As always, these can be accessed from the command palette. For some commands though, that are accessed very frequently during development, accessing them through the command palette can be too much friction. This is where keybindings can come into play.

Mapping a combination of keys to a certain piece of functionality in your package can be a good way to make a useful feature that much easier to access or invoke. Keybindings are great ways to enhance a package, but abusing and overusing them can quickly result in a pollution of the keybinding space with packages stepping on one another toes and perhaps those of Atom's core functionality as well. Only once you are certain that a particular command deserves a keybinding should you add it.

### Adding A Keybinding For A Command

... // assuming a command attached to some feature, explain how to assign a keybinding to that command.

### Keybinding Conventions

There is currently no official convention enforced or even recommended for assigning keybindings within your package. There are, however, some guidelines that will suffice as conventions for now. You should follow these guidelines when assigning keybindings.

- The `cmd` key should only be used in keybindings for Atom's core functionality.
- The combination of `cmd-alt-ctrl` in a keybinding usually signifies that it is related to developing Atom or Atom packages.
- The combination of `cmd-k` makes a key-chord that, followed by any of a number of keys, will trigger a variety of core Atom functionality.

When it comes to assigning bindings to your own packages:

- You should avoid using the `cmd` key. Just don't use it.
- Try to pick a unique keybinding, something that you haven't already encountered in existing, popular third party packages.
- If you expect to have a series of commands with keybindings, try taking the key-chord approach. For instance, start with `ctrl-x` and then a variety of keys (e.g. `1`, `2`, `3`, `4`) can follow for each of your series of commands.
- Before settling on a particular keybinding, test it out with the *Keybinding Resolver* package to see if it is in direct conflict with anything that you obviously don't want to clash with.

[Corey Johnson](https://github.com/probablycorey) reminds us of perhaps the best convention of all when it comes to keybindings,

> When I'm writing a package I try and avoid creating a keybinding and just focus on the commands. If a user wants to use a keybinding instead of using the command palette they can set that up themselves.

[source](http://discuss.atom.io/t/keymap-style-guide/4432)

### Checking For Clashes in Keybindings

There is a handy package that ships with Atom, *Keybinding Resolver*, that allows you to check to what certain keybindings are resolving. And more importantly, it also tells you what commands are not being triggered because of conflicting bindings.

You can open *Keybinding Resolver* with `cmd-.`. From there start tapping different keybindings to see where things stand. This is particularly useful for making sure your own packages aren't conflicting with core functionality or popular packages with important functionality.