#More information on APM, the Atom Package Manager.

APM is built on Node Package Manager, or `npm`. At first glance they are almost
identical, sharing most of the core commands to manage and publish packages.

## Configuring apm & npm
Atom packages are stored on GitHub, however, many of these packages also rely
on third-party Node packages stored on `npm`.

Like `npm`, `apm` is configurable. `npm` uses files in your home folder
called `.npmrc` to store configuration on a user-to-user basis. There is no
official documentation for `apm` yet, but wanting to use a different `npm`
registry for apm packages that require `npm` dependencies, I wanted to find
the equivalent of `.npmrc` for `apm`.

As most Atom assets are stored in the application itself on OS X, I dug through
it and found the `atom_package_manager` directory in
`/Applications/Atom.app/Contents/Resources/app/apm/node_modules/atom-package-manager`.
If you place an `.apmrc` file in this directory, it will be picked up by `apm`.
The syntax for `.apmrc` is as far as I can tell identical to `.npmrc` files.
[the npm site](https://www.npmjs.org/doc/files/npmrc.html) has more details.
To see what kind of configuration options are available, again, check out
[npm's stellar docs](https://www.npmjs.org/doc/misc/npm-config.html).
I can't guarantee that all of these will work, but the registry option does.

So, since using the European registry mirror [npmjs.eu]() is typically
significantly faster if you live in Europe, I wanted to change the registry for
`apm` like I have for `npm` for when `apm` needs to pick up Node packages. All
you need to do is to edit the file (let's use Atom for this!):
`atom /Applications/Atom.app/Contents/Resources/app/apm/node_modules/atom-package-manager/.apmrc`
This will bring up the file in Atom. Mine already had a cache location
configured (`cache = ~/.atom/.apm`), so to add a new setting just put your
setting on the next file: `registry = http://registry.npmjs.eu/`

Once you have configured your `.apmrc` to your heart's content, save the file.
`apm` should pick up on this immediately, and you're good to go!
