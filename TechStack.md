Atom Technology Stack
==========

Atom is built from ground up using extendible web technologies. Atom is a specialized variant of Chromium - each window is a locally-rendered web page. How do they do it? Here's what's Atom is built of:

### [Node](http://nodejs.org) - Backend/Processes

...

### [Node webkit](https://github.com/rogerwang/node-webkit) - Node.js to Native app

...

### [CoffeeScript](http://www.coffeescript.org) - Logic

...

### [SpacePen](http://www.github.com/atom/space-pen) - Templating

...

### [Less](http://www.lesscss.org) - Styling

Although it would be best to add styles in any type of language, *Less* is used for Atom for two primary reasons (according to [nathansobo](http://discuss.atom.io/users/nathansobo)):

 - SASS is a favorite here at GitHub, but it's implemented in Ruby, and we wanted to ship with a default format that had no external dependencies.
 - LESS is used by bootstrap which we leaned on as the foundation of our styles. Opinions vary, but bootstrap has a lot of traction and GitHub employs one of its developers, so we thought it was a reasonable choice.

[Source](http://discuss.atom.io/t/sass-instead-of-less/221/12)

### [CSON](https://github.com/bevry/cson) - Configuration

...

### [Jasmine](http://jasmine.github.io/) - Testing

...

--------

Official Blog Post - [The Nucleus of Atom](http://blog.atom.io/2014/02/26/the-nucleus-of-atom.html)
