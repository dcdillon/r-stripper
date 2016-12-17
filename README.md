# r-stripper [![Build Status](https://travis-ci.org/dcdillon/r-stripper.svg?branch=master)](https://travis-ci.org/dcdillon/r-stripper)

### Description

R, on some platforms, leaves debugging symbols in the shared libraries it creates when building packages.  This can cause significantly bloated libraries (especially when templates are used).  r-stripper interrogates R about what linkers it will use when creating shared libraries.  If it finds that you are using linkers that accept a command line option to strip debuging symbols, it will add that configuration to your `src/Makevars` file.  If you don't have a `src/Makevars` file, it will create one at build time.

### Usage

In your package, create an `inst/tools/r-stripper` directory.  Place `stripper` and `stripper.R` there.
From your `configure` file, call `inst/tools/r-stripper/stripper`.

### Supported Linkers

Currently `r-stripper` only supports GNU `ld`, GNU `gold`, and `Solaris Link Editors` for debug symbol stripping.  Adding others is fairly trivial, but I simply don't have access to them.  Pull requests are welcome.

### Author

Daniel C. Dillon

### License

GPL (>= 2)
