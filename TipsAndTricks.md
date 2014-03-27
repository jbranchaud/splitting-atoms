---
layout: page
title: Tips and Tricks
---

Atom is powerful tool with lots of features and capabilities. Here is a
collection of tips and tricks for quickly taking advantage of Atom.

## Contents

- [Fuzzy File Finder](#FuzzyFileFinder)
- [Git + Fuzzy File Finder](#GitFuzzyFileFinder)

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
