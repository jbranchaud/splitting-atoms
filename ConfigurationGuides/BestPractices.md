# Best Practices for Atom Configurations

A collection of best practices to use when defining the various parts of
your Atom configuration including:

- `config.cson`
- `init.coffee`
- `keymap.cson`
- `snippets.cson`
- `styles.less`

## General Configuration Best Practices

...

## `config.cson`

...

## `init.coffee`

### Keep your scripts organized

Whether you keep all your scripts in the `init` file or separate them out
into files, always keep them organized. They should be organized by the
language or technology for which they are used. Use comments to make clear
the purpose of a set of scripts. This will make it easier for you to
maintain them and will make them more accessible to others who may want to
use parts of your `init.coffee` (assuming you make it publicly accessible).

### Maintain a clean, modular init file

In order to maintain an `init.coffee` file that is easy to read and
maintain, it is recommended that you be as modular as possible. If you
have more three or more blocks of code in your `init` file that are specific
to a particular language or a certain type of development, consider moving
it to a separate file that is then *required* by your `init` file.

For instance, if you wrote a couple commands and helper scripts that you use
when working with JSON files, you should move those to something like
`json-init.coffee` and then require that in `init.coffee`.

For a more detailed explanation of this practice, read
[Modularizing Atom Init Scripts](http://joshbranchaud.com/blog/2014/03/03/Modularizing-Atom-Init-Scripts.html).

## `keymap.cson`

...

## `snippets.cson`

...

## `styles.less`

...
