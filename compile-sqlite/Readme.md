- Compile sqlite with icu

``` bash
CFLAGS='-O3 -DSQLITE_ENABLE_ICU' CPPFLAGS=`icu-config --cppflags` LDFLAGS=`icu-config --ldflags` ./configure
```

- Steps for compile 

``` bash
    tar xzf sqlite.tar.gz    ;#  Unpack the source tree into "sqlite"
    mkdir bld                ;#  Build will occur in a sibling directory
    cd bld                   ;#  Change to the build directory
    ../sqlite/configure      ;#  Run the configure script
    make                     ;#  Run the makefile.
    make sqlite3.c           ;#  Build the "amalgamation" source file
    make test                ;#  Run some tests (requires Tcl)
```