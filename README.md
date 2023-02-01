# Brotli amalgamation

This repository contains amalgamations of the Brotli C library.
 - Header files remain mostly as they are, other than editing include directives.
 - Source files are merged into a single compilation unit.

You can compile the single .c file and use .h files without editing the include path. All paths are relative. So even the simplest compiler invocation works:

    gcc -c brotli.c -o brotli.o


## Why?

 - Because a single .c file is very easy to add to any project and have it compile on any platform with any compiler.

 - Because the redundancy in the C compilation model makes building many files very slow. Of course you don't _have_ to rebuild the library every time if you use an incremental build. But a full rebuild isn't rare, and amalgamations speed it up substantially.
