## r-stripper

### Description

R, by default, leaves debugging symbols in the shared libraries it creates when building packages.  This can cause significantly bloated libraries (especially when templates are used).  r-stripper interrogates R about what linkers it will use when creating shared libraries.  If it finds that you are using linkers that accept a command line option to strip debuging symbols, it will add that configuration to your `src/Makevars` file.  If you don't have a `src/Makevars` file, it will create one at build time.

### Usage

In the `configure` file for an R package, add a line at the end that calls `stripper`.  Alternatively, the code from the `stripper` file can be pasted directly in to your `configure` file (preferably as the last thing that happens).

### Supported Linkers

Currently `r-stripper` only supports `gcc`, `g++`, `clang`, or `clang++` for debug symbol stripping.  Adding others is fairly trivial, but I simply don't have access to them.  Pull requests are welcome.

### Author

Daniel C. Dillon

### License

GPL (>= 2)
