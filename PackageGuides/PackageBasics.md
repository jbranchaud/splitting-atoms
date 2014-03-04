#Package Basics

This document describes all the parts of a package in an attempt to make it easier to develop your own.

##Atom Technology Stack

- [CoffeeScript](http://www.coffeescript.org) - Logic
- [SpacePen](http://www.github.com/atom/space-pen) - Templating
- [Less](http://www.lesscss.org) - Styling
- [CSON](https://github.com/bevry/cson) - Configuration
- [Node](http://nodejs.org) - Backend/Processes
- [Jasmine](http://jasmine.github.io/) - Testing

Note: Though CoffeeScript and CSON are the defaults in package development,
JavaScript and JSON can easily be used in their place. Pick the language that
works best for you.

##Package Structure

* /keymaps/ - `Key Mapping Directory`
 * your-package.cson - `Key Mappings`
* /lib/ - `Source Folder`
 * your-package-view.coffee - `Package View Source`
 * your-package.coffee - `Package Source`
* /menus/ - `Menu Mapping Directory`
 * your-package.cson - `Menu Mappings`
* /spec/ - `Test Directory`
 * your-package-spec.coffee - `Main Source Test`
 * your-package-view-spec.coffee - `Main View Test`
* /stylesheets/ - `Style Directory`
 * your-package.less - `Package Styles
* package.json - `Package Information`

##Getting Started

You can generate a new package with the above structure by opening Atom, keying `cmd+shift+p` and selecting `Package Generator - Generate Package`

This will create a project, link it, and open it in Atom.

##Workflow Tips
Use `cmd+opt+i` to open DevTools

In DevTools, open the console and type `atom` and hit enter.
Now you can see all the methods and data available to you within the atom namespace.

After making changes, use `ctrl+opt+cmd+l` to reload your window.

Open the atom command palette (`cmd+shift+p`), and select `Styleguide: Show`.
This will help you structure your package and implement views. It is also wildly helpful for theme development.

If you want to get a look at the classes you are extending/using, open up `Atom.app/Contents/Resources/src/` and have a look around.

##Common Tasks

#### Getting the current editor

`editor = atom.workspace.getActiveEditor()`

#### Getting the current path

`path = atom.project.path`

#### Getting the current file

`file = atom.workspace.getActiveEditor().getBuffer().file.path`

#### Getting the current selection

`selection = atom.workspace.getActiveEditor().getSelectedText()`

#### Triggering package events

`atom.workspaceView.trigger('your-package:toggle')`
