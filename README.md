# The BioJulia Package Registry

The registry for julia packages developed and released by BioJulia for
bioinformatics and computational biology.

Package registries are used by Julia's package manager
[Pkg.jl](https://julialang.github.io/Pkg.jl/v1/) and include information about
packages such as versions, dependencies and compatibility constraints.

This registry primarily contains BioJulia packages, but it is open for everyone
to use if their group have written a package or tool for bioinformatics;
particularly those that use, or are designed to work with BioJulia tools.

## Registering a package in the BioJulia registry

New packages and new versions of packages are added by pull requests against
[this project's GitHub repository](https://github.com/BioJulia/BioJuliaRegistry).
It is **highly** recommended that you use BioJulia's installation of
Registrator.jl to automate the process.

## FAQ

## Disclaimer

This registry is primarily used by BioJulia, **but** since it is open for anyone to
register packages in **we do not provide any official endorsement or guarantee**.

**The maintainers of this registry are not responsible for the code you install
through this registry**.

**You are still responsible for reviewing your own code dependencies, and their
licenses/terms**.

After all BioJulia is still an open-source project, run by academics that
volunteer in their free time.