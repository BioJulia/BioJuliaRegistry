# <img align="right" src="./sticker.svg" width="30%"> The BioJulia Package Registry

[![Build Status](https://travis-ci.com/BioJulia/BioJuliaRegistry.svg?branch=master)](https://travis-ci.com/BioJulia/BioJuliaRegistry)

The registry for julia packages developed and released by BioJulia for
bioinformatics and computational biology.

Package registries are used by Julia's package manager
[Pkg.jl](https://julialang.github.io/Pkg.jl/v1/) and include information about
packages such as versions, dependencies and compatibility constraints.

This registry primarily contains BioJulia packages, but it is open for everyone
to use if their group have written a package or tool for bioinformatics;
particularly those that use, or are designed to work with BioJulia tools.


## Make your julia installation aware of this registry

To install any packages released through this registry, you will need to make
your julia installation's package manager aware of it.
It's a piece of cake!

Start the julia terminal, hit the `]` key to enter pkg mode (you should see the
prompt change from `julia> ` to `pkg> `), then enter the following command:

```julia
registry add https://github.com/BioJulia/BioJuliaRegistry.git
```

After you've added the registry, you can install BioJulia packages just as you
would any other.

These instructions are included in the README and manuals for each package
released through this registry, and is also described in the getting started
section of our [website](https://biojulia.net/getting-started/).


## Registering a package in the BioJulia registry

New packages and new versions of packages are added by pull requests against
[this project's GitHub repository](https://github.com/BioJulia/BioJuliaRegistry).
It is **highly** recommended that you use BioJulia's installation of
Registrator.jl to automate the process.

You can install BioJulia's Registrator for your package by visiting its page
[here](https://github.com/apps/biojulia-package-registrar).

After that, you can release your package as follows:

1. Set the (Julia)Project.toml version field in your repository to your new desired version.
2. Comment `@BioJuliaBot register` on the commit/branch you want to register (e.g. like here or here), and the BioJuliaBot will make a PR to this registry for you. It will reply to you, with a link to the PR. More details are provided for this step below.
3. If something is incorrect, adjust, and redo step 2.
4. If the automatic PR tests pass, but a moderator makes suggestions (e.g., manually updating your (Julia)Project.toml to include a [compat] section with version requirements for dependancies), then incorporate suggestions as you see fit into a new commit, and redo step 2 for the new commit. You don't need to do anything to close out the old request.
5. Finally, once the PR is accepted merged into the registry, tag a release through GitHub releases on your repository. The BioJuliaBot should comment on your accepted PR, telling you how.

Registrator will look for the project file in the master branch by default, and will use the version set in the (Julia)Project.toml file via, for example, version = "0.1.0". To use a custom branch comment with:

`@BioJuliaBot register branch=name-of-your-branch`

The old pseudo-Julia syntax is also still supported:

`@BioJuliaBot register(branch="foo")`

### Details for triggering JuliaRegistrator (for step 2 above)

Either:

- Open an issue and add `@BioJuliaBot register` as a comment. You can re-trigger the bot by commenting `@BioJuliaBot register` again (in case the bot reports an error or to make changes).
- Add a comment to a commit and say `@BioJuliaBot register`.

_Note_: Only _collaborators_ on the package repository and _public members_ of an organization the package is under are allowed to register it.
If you are not a collaborator, you can request a collaborator do it for you.

## FAQ

### Where do I report a problem with a package in the General registry?

Please **do not** report it as an issue here. Even if it is a BioJulia developed
package. Please find the GitHub repository for the package and file an issue there.

### My pull request has a merge conflict, what do I do?

Retrigger Registrator.


### How do I retrigger Registrator in order to update my pull request?

Do what you did when you triggered Registrator the first time.


### Are there any requirements for package names in the General registry?

There are no hard requirements, but it is highly recommended to follow the package naming guidelines.


### What to do when asked to reconsider/update the package name?

If someone comments on the name of your package when you first release it it is often because it does not follow the naming guidelines.
If you think that your package should not follow those conventions for some reason or another, just explain why.
Otherwise, it is often a good idea to just rename the package -- it is more disruptive to do so after it is already registered, and sticking to the conventions makes it easier for users to navigate Julia's many varied packages.

As long as the package is not yet registered, renaming the package from OldName.jl to NewName.jl is reasonably straightforward:

- Rename the GitHub repository to NewName.jl
- Rename the file src/OldName.jl to src/NewName.jl
- Rename the top-level module to NewName
- Update tests, documentation, etc, to reference the new name


### How do I rename an existing registered package?

Technically, you can't rename a package once registered, as this would break existing users.
But you can re-register the package again under a new name with a new UUID.
Which has basically the same effect.

- Follow the instructions above for renaminging a package: rename on GitHub, rename files etc.
- Generate a new UUID for the Project.toml
- Increment the version in the Project.toml as a breaking change.
- Register it as if it were a new package
- Comment on the PR, that this is a rename.
- It will have to go though the normal criteria for registering a new package.
    - In particular, even if you get it merged manually, it will need to wait 3 days from the PR being opened.
    - This gives others and yourself the chance to point out any naming issues.

You also should let your users know about the rename, e.g. by placing a note in the README, or opening PRs/issues on downstream packages to change over.

## Disclaimer

This registry is primarily used by BioJulia, **but** since it is open for anyone to
register packages in **we do not provide any official endorsement or guarantee**.

**The maintainers of this registry are not responsible for the code you install
through this registry**.

**You are still responsible for reviewing your own code dependencies, and their
licenses/terms**.

After all, BioJulia is still an open-source project, run by academics that
volunteer in their free time.

## Contributing

We appreciate contributions from users including reporting bugs, fixing
issues, improving performance and adding new features.

Take a look at the [contributing files](https://github.com/BioJulia/Contributing)
detailed contributor and maintainer guidelines, and code of conduct.


### Financial contributions

We also welcome financial contributions in full transparency on our
[open collective](https://opencollective.com/biojulia).
Anyone can file an expense. If the expense makes sense for the development
of the community, it will be "merged" in the ledger of our open collective by
the core contributors and the person who filed the expense will be reimbursed.


## Backers & Sponsors

Thank you to all our backers and sponsors!

Love our work and community? [Become a backer](https://opencollective.com/biojulia#backer).

[![backers](https://opencollective.com/biojulia/backers.svg?width=890)](https://opencollective.com/biojulia#backers)

Does your company use BioJulia? Help keep BioJulia feature rich and healthy by
[sponsoring the project](https://opencollective.com/biojulia#sponsor)
Your logo will show up here with a link to your website.

[![](https://opencollective.com/biojulia/sponsor/0/avatar.svg)](https://opencollective.com/biojulia/sponsor/0/website)
[![](https://opencollective.com/biojulia/sponsor/1/avatar.svg)](https://opencollective.com/biojulia/sponsor/1/website)
[![](https://opencollective.com/biojulia/sponsor/2/avatar.svg)](https://opencollective.com/biojulia/sponsor/2/website)
[![](https://opencollective.com/biojulia/sponsor/3/avatar.svg)](https://opencollective.com/biojulia/sponsor/3/website)
[![](https://opencollective.com/biojulia/sponsor/4/avatar.svg)](https://opencollective.com/biojulia/sponsor/4/website)
[![](https://opencollective.com/biojulia/sponsor/5/avatar.svg)](https://opencollective.com/biojulia/sponsor/5/website)
[![](https://opencollective.com/biojulia/sponsor/6/avatar.svg)](https://opencollective.com/biojulia/sponsor/6/website)
[![](https://opencollective.com/biojulia/sponsor/7/avatar.svg)](https://opencollective.com/biojulia/sponsor/7/website)
[![](https://opencollective.com/biojulia/sponsor/8/avatar.svg)](https://opencollective.com/biojulia/sponsor/8/website)
[![](https://opencollective.com/biojulia/sponsor/9/avatar.svg)](https://opencollective.com/biojulia/sponsor/9/website)


## Questions?

If you have a question about contributing or using BioJulia software, come
on over and chat to us on [Gitter](https://gitter.im/BioJulia/General), or you can try the
[Bio category of the Julia discourse site](https://discourse.julialang.org/c/domain/bio).