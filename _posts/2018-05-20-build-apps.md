---
layout: post
title: Notes on build tools
---

## gcc

List where gcc is searching for header files
```bash
# For C++
`gcc -print-prog-name=cc1plus` -v
# For C
`gcc -print-prog-name=cc1` -v
```

## Autotools

List options

```bash
./configure --help
```

Specify local directory to install application

```bash
# Note, path has to be absolute
./configure --prefix=<absolute installation path>

# Compile with number of jobs
make -j <number of jobs>

# This will install to the path given by --prefix
make install
```

Ways to add directories to search for include headers or libraries
by exporting them before use or setting them in the `.profile` file.

```bash
C_INCLUDE_PATH="<path 1>:<path 2>:$C_INCLUDE_PATH"
CPLUS_INCLUDE_PATH="<path 3>:<path 4>:$CPLUS_INCLUDE_PATH"
LIBRARY_PATH="<path 7>:$LIBRARY_PATH"
CFLAGS = "-I<some path to headers> -I <some other path>"
LDFLAGS = "-L<some path>"
```

## CMake
Change values of variables

```bash
cmake <path to CMakeLists.txt> -D<var1>=<value 1> -D<var2>=<value 2>
make
```
