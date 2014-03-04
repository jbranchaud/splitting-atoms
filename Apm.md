# More information on APM, the Atom Package Manager.

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

## APM command-line options

### Configuring APM
##### Options:
 - `--version`, `-v` Print the apm version
 - `--help`, `-h` Print usage message
 - `--color` Enable colored output `[boolean] [default: true]`

### Installing, removing and configuring packages
#### `apm featured`
List the Atom packages/themes that are currently featured in the [Atom.io]() registry.

##### Options:
- `--themes`, `-t` Only list themes `[boolean]`
- `--compatible`, `-c`, Only list packages/themes compatitle with this Atom version `[string]`
- `--json` Output featured packages as JSON array `[boolean]`

#### `apm install <package_name>`
Install the given Atom package. If you don't specify a package name, Atom will
attempt to install all the dependencies listed in the `package.json` files
into a directory called `node_modules` under your current working directory.

##### Options:
- `--silent`, `-s` Set the npm log level to silent `[boolean]`
- `--quiet`, `-q` Set the npm log level to warn `[boolean]`

#### `apm list`
List all of the installed packages. Includes all packages included with Atom.

##### Options:
- `--themes` Only list themes `[boolean]`

##### Aliases:
- `apm ls`

#### `apm search <package_name>`
Searches matching packages published on the Atom.io registry.

##### Options:
- `--json` Output matching packages as JSON array `[boolean]`

#### `apm view`
View information about a single package published on the Atom.io registry.

##### Options:
- `--json` Output featured packages as JSON array `[boolean]`

##### Aliases:
- `apm show`

#### `apm uninstall <package_name>`
Uninstall the matching package from your packages directory.

##### Options:
- `--dev` `-d`, Uninstall from your dev packages directory. `[boolean]`
- `--hard`, Uninstall from your dev packages *and* regular packages directory. `[boolean]`

### Creating, managing, and publishing packages

#### `apm clean`

Deletes all packages in the `node_modules` folder that are not referenced as a dependency in the `package.json` file.

#### `apm dedupe`

Reduce duplication in the `node_modules` folder in the current directory.

#### `apm dev`

Clone the given package's Git repository to `~/github/<package_name>`, install its dependencies, and link it for development to `~/.atom/packages/dev/<package_name>`.

Once this command completes you can open a dev window from atom using `cmd-shift-o` to run the package out of the newly cloned repository.

#### `apm develop`

Same as `apm dev`

#### `apm init`

Generates code scaffolding for either a theme or package depending on option selected.

##### Options:
- `--package`, `-p` Generates a basic package `[string]`
- `--theme`, `-t` Generates a basic theme `[string]`
- `--convert`, `-c` Path or URL to TextMate bundle/theme to convert `[string]`

#### `apm link`

Create a symlink for the package in `~/.atom/packages`. The package in the current working directory is linked if no path is given.

Run `apm links` to view all the currently linked packages.

##### Options:
- `--dev`, `-d` Link to `~/.atom/dev/packages` `[boolean]`

#### `apm linked`

Same as `apm link`

#### `apm links`

List all of the symlinked atom packages in `~/.atom/packages` and `~/.atom/dev/packages`.

#### `apm ln`

Same as `apm links`

#### `apm lns`

Same as `apm links`

#### `apm login`

Create and save a GitHub OAuth2 token to the keychain. This token will be used to identify yourself when publishing packages to atom.io.

##### Options:
- `--user`, `-u` GitHub username or email `[string]`

#### `apm publish`

Publish a new version of the package in the current working directory.

If a new version or version increment is specified, then a new Git tag is created and the `package.json` file is updated with that new version before it is published to the apm registry. The HEAD branch and the new tag are pushed up to the remote repository automatically using this option.

Run `apm featured` to see all the featured packages or `apm view <packagename>` to see information about your package after you have published it.

##### Options:
- `--tag`, `-t` Specify a tag to publish `[string]`

#### `apm rebuild`

Rebuild all the modules currently installed in the `node_modules` folder in the current working directory.

#### `apm test`

Runs the package's tests contained within the spec directory (relative to the current working directory).

##### Options:
- `--path`, `-p` Path to atom command `[string]`

#### `apm unlink`

Delete the symlink in `~/.atom/packages` for the package. The package in the current working directory is unlinked if no path is given.

Run `apm links` to view all the currently linked packages.

##### Options:
- `--dev`, `-d` Unlink package from `~/.atom/dev/packages` `[boolean]`
- `--hard` Unlink package from `~/.atom/packages` and `~/.atom/dev/packages` `[boolean]`
- `--all`, `-a` Unlink all packages in `~/.atom/packagea` and `~/.atom/dev/packages` `[boolean]`

#### `apm unpublish`

Remove a published package from the atom.io registry. The package in the current working directory will be unpublished if no package name is specified.

##### Options:
- `--force`, `-f` Do not prompt for confirmation. `[boolean]`

#### `apm update`

Run `apm clean` followed by `apm install`.

See `apm help clean` and `apm help install` for more information.