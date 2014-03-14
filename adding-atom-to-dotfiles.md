---
layout: page
title: Adding Atom to Your Dotfiles
---

Keeping all your dotfiles and system configurations together, under version control, and stored somewhere accessible (say on GitHub) is a good practice. It allows you to easily access and install everything from bash/zsh settings to environment variables to git aliases (and more) across all your machines. Plus others can use clever bits and pieces from your dotfiles in their own. Why not include your Atom files (those in `~/.atom`) in all of this?

If you don't know what dotfiles are or you don't already have your own dotfiles setup, [GitHub can help get you up to speed](http://dotfiles.github.io/).

## What to include

We recommend that you store `config.cson`, `init.coffee`, `keymap.cson`, `snippets.cson`, and `styles.less` in your dotfiles. The `packages/` and `storage/` directories should not be included. In fact you will even want to add them to your `.gitignore` file.

## How to include them

There are as many ways to include these in your dotfiles as there are ways to setup your dotfiles. We are not going to go through all of them here. A common approach to having a dotfile configuration installed is with symlinks. This is the approach we will discuss.

First, figure out the naming scheme for directories that is used by your installation script. It is likely either `directory.symlink` or `.directory`.

Move the `~/.atom` directory to your dotfiles directory renaming it according to the appropriate naming scheme. For example,

    mv ~/.atom ~/.dotfiles/atom.symlink

Following the naming scheme is important because that is the basis on which your installation script will decide what to symlink.

Now test out that things are working properly. Run your installation script and then check if there again exists `~/.atom`. If you run `ls -la ~` you should be able to see if it is there. You will also notice that it tells you the directory that it is symlinked to. Success.

You can now commit the files we discussed above to your dotfiles repository. At this point you should be all set and ready to go.

## Concerns

You may be wondering if there is any risk in committing certain data from `config.cson` to a public repository. Values like the `userId` values under `exception-reporting` and `metric` might look like they contain sensitive information. Fortunately, these are hashed values that won't reveal anything sensitive ([exception-reporting source](https://github.com/atom/exception-reporting/issues/7), [metrics source](https://github.com/atom/metrics/issues/18)). In other words, you should be able to commit that file as is.