---
layout: page
title: Tips and Tricks
---

Atom is powerful tool with lots of features and capabilities. Here is a
collection of tips and tricks for quickly taking advantage of Atom.

## Contents

- [Keybinding Precedence](#KeybindingPrecedence)
- [Debugging Keybindings](#DebuggingKeybindings)
- [Fuzzy File Finder](#FuzzyFileFinder)
- [Git + Fuzzy File Finder](#GitFuzzyFileFinder)

## <a name="#KeybindingPrecedence" href="#KeybindingPrecedence">Keybinding Precedence</a>

When adding custom keybindings to your own configuration or including
keybindings in the package you are creating, it is helpful to understand the
precedence of keybindings.

There are two factors that play into keybinding precedence:

- 1. When the keybinding is registered, relative to other keybindings
- 2. The scope that the keybinding is tied to (e.g. `.editor`)

As for the first, the last keybinding loaded wins. If two packages register
`ctrl-t`, the package that is loaded second will take precedence. The
keybinding of the first package will be registered and subsequently
inhibited by the same keybinding registered by the second package. If
keybindings for core or third-party packages aren't working as expected,
this is likely the culprit. See
<a href="#DebuggingKeybindings">Debugging Keybindings</a> for hints on how to
hunt this down. Also, custom keybindings declared in your configuration, in
`keymap.cson`, will take precedence over everything.

As for the second, the keybinding with the more specific scope wins. If
there are two conflicting keybindings as illustrated in the previous
paragraph, but one is more specific, it will take precedence, but only if it
is in the correct context. Here is a concrete example to help clarify.

Package-1 declares the following keybinding:

    '.platform-darwin':
      'ctrl-t': 'some:command'

Package-2 declares the following keybinding:

    '.editor':
      'ctrl-t': 'another:command'

Given these two packages, if we press `ctrl-t` while focused on an editor,
it doesn't matter the order in which they were loaded, the keybinding
declared by Package-2 will be triggered (i.e. `another:command`). However,
if we are focused on, say, the Tree-View, then the keybinding declared by
Package-1 will be triggered (i.e. `some:command`). The take away here is
that you should use as specific of a scope as is appropriate for you
keybindings.

## <a name="DebuggingKeybindings" href="#DebuggingKeybindings">Debugging Keybindings</a>

There are lots of keybindings and it can be hard to keep them all straight. Some are defined by packages that come with Atom, others by packages you have installed, and you may also be testing out a few of your own with a package you are currently developing. To quickly see what command is triggered by a particular keybinding as well as what commands are being inhibited, use the *Keybinding Resolver*.

Activate the *Keybinding Resolver* with `Cmd-.`.

A small window will display at the bottom of the editor informing you on each key press of the associated command.

- Try pressing the command palette keybinding, `Cmd-shift-P`. It will resolve to the `command-palette:toggle` command.

- Try pressing the *backspace* (or *delete*) button within an editor. It will resolve to `core:backspace`, but will also show commands that it takes precedence over.

Any time you have questions about some keybindings, the *Keybinding Resolver* is a good place to start looking.

## <a name="FuzzyFileFinder" href="#FuzzyFileFinder">Fuzzy File Finder</a>

Atom has a fuzzy file finder much like Sublime Text's, and is incredibly
powerful. Simply type `⌘-T` or `⌘-P` to bring it up, and start searching for
files or folders.

You don't have to specify the exact directory or filename, it's generally smart
enough to work out what you mean. i.e.: typing `vie la ma` in the fuzzy file
finder will work out you're probably looking for the file
`app/views/layouts/main.blade.php`.

![An example of the fuzzy file finder in Atom](http://i.imgur.com/CiyBqTc.png)

Used correctly, you will probably not need to use the sidebar much if you know
the project you're working on.

This will ignore any pattern that you have specified in your *Ignored Names*
preference.

## <a name="GitFuzzyFileFinder" href="#GitFuzzyFileFinder">Git + Fuzzy File Finder</a>

If you use Git, the fuzzy file finder can display any modified or untracked file
in your project. It works pretty much like running `git status` and is useful
for tracking the current state of your project. To trigger this, type
`⌘-shift-B`.
![An example of the fuzzy file finder in Git](http://i.imgur.com/SY4j5nr.png)
