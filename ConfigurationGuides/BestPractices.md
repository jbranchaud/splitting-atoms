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
