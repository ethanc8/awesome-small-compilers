# Small C compilers

Includes free/open compilers which are written in languages which have small compilers, or in standard C.

cproc seems to be generally the most promising - it's actively maintained, uses a backend which is useful for other languages, and is already at C17 support and working on C23.

For more obscure ISAs, other compilers would be more useful.

Although it only supports x86_64, chibicc is probably the most well-documented - it was written to accompany a book about implementing compilers, and each commit implements a feature.

## Production-quality small compilers

* [Small Device C Compiler](https://sdcc.sourceforge.net/) - C23 compiler for microprocessors, with ISO C committee members working on it
  * ISAs: various microprocessors
  * [HF discussion](https://news.ycombinator.com/item?id=11036994)
* [Tiny C Compiler (tcc)](https://repo.or.cz/w/tinycc.git) - C90 compiler, implements most of C99 and some GNU C extensions, not optimizing
  * ISAs: x86_32, x86_64, ARM 32-bit, RISC-V 64-bit
  * Assembler and linker are included in tcc
* [Portable C Compiler](https://web.archive.org/web/20231212090621/http://pcc.ludd.ltu.se/) - derivative of the second Bell Labs C compiler, fully supports C99, also has a partial Fortran 77 frontend
  * ISAs (stable): x86_32, x86_64
  * Supported OSes: Windows, GNU/Linux, OS X, FreeBSD, NetBSD, Solaris 10
  * HN discussions:
    * [2009](https://news.ycombinator.com/item?id=1021299)
    * [2011](https://news.ycombinator.com/item?id=2402382)

## Small optimizing compilers

* [cproc](https://sr.ht/~mcf/cproc/) - implements most of C11, QBE backend
  * ISAs: amd64, arm64, riscv64
  * Target OSes: linux-musl, linux-gnu, FreeBSD
  * Implements parts of GNU C and C23
  * Written in C99
* [cparser](https://github.com/libfirm/cparser) - implements most of C99, libfirm backend
  * ISAs (mature): x86_32, SPARC
  * ISAs (experimental): x86_64, ARM
  * Written in C99

## Transpilers

* [Cake](http://thradams.com/cake/index.html) - C23 to C99 transpiler
  * Also implements some WG14 proposals and some of its own extensions
  * Has an ownership, nullability, etc checker
  * [HN discussion](https://news.ycombinator.com/item?id=32823118)

## Small non-optimizing compilers

* [TenDRA tdfc2](http://www.tendra.org/) - implements all of C90 and C++98, TenDRA IR backend
  * ISAs: alpha, hppa, m68k, MIPS, PowerPC, SPARC, x86_32
  * See [trans(1)](http://www.tendra.org/trans.1/) for supported ABIs
* [kefir](https://sr.ht/~jprotopopov/kefir/) - complete C17 compiler
  * ISAs: amd64
  * Target OSes: Linux, FreeBSD, OpenBSD, NetBSD, theoretically any SysV ABI system
  * Written in C11
* [chibicc](https://github.com/rui314/chibicc) - educational C11 compiler, designed to be easy to read
  * [chibicc book in Japanese](https://www.sigbus.info/compilerbook), [English translation (might be machine-translated)](https://www.ocf.berkeley.edu/~stefan/fun/chibicc.html)
* [slimcc](https://github.com/fuhsnn/slimcc) - chibicc fork which makes faster code and has some C23 and GNU C features
* [Simple C Compiler (scc)](http://www.simple-cc.org/) - implements most of C99, has native and QBE backends
  * ISAs: x86_32, x86_64, ARM 32-bit
* [lacc](https://github.com/larmel/lacc) - implements all of C89
  * Written in C89
  * ISAs: x86_64
* [8cc eir](https://github.com/shinh/8cc/tree/eir) - 8cc fork which targets the [ELVM](https://github.com/shinh/elvm)
* [nwcc](https://nwcc.sourceforge.net/) - well-documented near-C90 compiler with some GNU C and C99 extensions, abandoned since 2014
* [Amsterdam Compiler Kit](https://tack.sourceforge.net/) - C90 compiler, abandoned since 2023
  * ISAs (well supported): i86, i386, 68000, i80, and VideoCore IV
  * ISAs (experimental): 6500, ARM, i80, Z80, Z8000, i86, i386, 68000, 68020, NS32016, SPARC, VAX4, PDP11 and VideoCore IV
  * Includes assembler and linker
  * Platforms: pc86, linux386, linux68k, linuxppc, linuxmips, cpm, rpi (VideoCore IV), pdpv7, msdos86 and msdos386
  * Frontends: ANSI C, B, Pascal and Modula-2
  * Written in C90
* Plan 9 C compiler - near-C90 compiler
  * Overview articles
    * [How to Use the Plan 9 C Compiler](https://p9f.org/sys/doc/comp.html)
    * [A Manual for the Plan 9 assembler](https://p9f.org/sys/doc/asm.html)
      * [Inferno version](https://www.vitanuova.com/inferno/papers/asm.html)
    * [Plan 9 C Compilers](https://p9f.org/sys/doc/compiler.html)
      * [Inferno version](https://www.vitanuova.com/inferno/papers/compiler.html)
  * Toolchain components
    * (`8` represents the single character that designates the target architecture, which is `8` for i386)
    * [`cpp`](https://p9f.org/magic/man2html/1/cpp) - C90 preprocessor (Plan 9 dialect preprocessor is included in `8c`) - [`sys/src/cmd/cpp`](https://github.com/plan9foundation/plan9/tree/main/sys/src/cmd/cpp)
    * [`8c`](https://p9f.org/magic/man2html/1/8c) - C compiler - [`sys/src/cmd/8c`](https://github.com/plan9foundation/plan9/tree/main/sys/src/cmd/8c) and [`sys/src/cmd/cc`](https://github.com/plan9foundation/plan9/tree/main/sys/src/cmd/cc)
    * [`8a`](https://p9f.org/magic/man2html/1/8a) - Assembler for Plan 9 syntax - [`sys/src/cmd/8a`](https://github.com/plan9foundation/plan9/tree/main/sys/src/cmd/8a)
    * [`8l`](https://p9f.org/magic/man2html/1/8l) - Static linker - [`sys/src/cmd/8l`](https://github.com/plan9foundation/plan9/tree/main/sys/src/cmd/8l)
  * Plan 9 forks and other compiler sources
    * [Plan 9 Fourth Edition (MIT-licensed)](https://github.com/plan9foundation/plan9/tree/main)
      * ISAs: MIPS 3000 little-endian, MIPS 3000 big-endian, ARM 32-bit little-endian, x86_64, x86_32, PPC64, RISC-V 32, RISC-V 64, SPARC, PowerPC
      * Deprecated/abandoned ISAs: DEC Alpha, Motorola 68020, Motorola 68000, Intel 960, AMD 29000
      * Manpages: [`cpp`](https://p9f.org/magic/man2html/1/cpp) [`8c`](https://p9f.org/magic/man2html/1/8c) [`8a`](https://p9f.org/magic/man2html/1/8a) [`8l`](https://p9f.org/magic/man2html/1/8l)
    * [9legacy - small patchset to Plan 9](https://github.com/0intro/9legacy) - [homepage](http://9legacy.org/index.html)
    * [9front - most actively maintained Plan 9 fork](https://github.com/9front/9front) - [homepage](http://9front.org/)
      * ISAs: MIPS 3000 little-endian, MIPS 3000 big-endian, ARM 32-bit little-endian, ARM64, ARM THUMB, x86_64, x86_32, PPC64, RISC-V 32, RISC-V 64, SPARC, PowerPC
      * Manpages: [`2c`](http://man.9front.org/1/2c)
    * [Inferno (MIT-licensed)](https://github.com/inferno-os/inferno-os) - [homepage](https://www.vitanuova.com/inferno/)
      * ISAs: DEC Alpha, Motorola 68020, Motorola 68000, Intel 960, MIPS 3000 little-endian, MIPS 3000 big-endian, ARM 32-bit little-endian, x86_64, x86_32, SPARC, PowerPC
      * Manpages: [`2c`](https://www.vitanuova.com/inferno/man/10/2c.html)
    * [9-cc - Unix port based on Inferno and Plan 9 Fourth Edition (BSD-licensed)](https://github.com/0intro/9-cc)
    * [golang 1.4 (BSD-licensed)](https://github.com/golang/go/tree/release-branch.go1.4/src/cmd) - Go was originally another frontend `8g` on top of the Plan 9 toolchain, which was ported to other operating systems.
      * [More information about the switch from the Plan 9 toolchain](https://docs.google.com/document/d/1P3BLR31VA8cvLJLfMibSuTdwTuF7WWLux71CYD0eeD8/edit)
      * There have been quite significant changes
      * ISAs: x86_64, x86_32, ARM 32-bit little-endian
      * Supported OSes: DragonFly BSD, FreeBSD, Linux, NetBSD, OpenBSD, OS X (Darwin), Plan 9, Solaris and Windows

## Big C compilers

* [Digital Mars D](https://wiki.dlang.org/DMD) has a C compiler
  * [Article about it](https://briancallahan.net/blog/20220704.html)
* 

## Bootstrapping-only compilers

## Source-available nonfree small compilers

* [CompCert C Compiler (ccomp)](https://compcert.org/compcert-C.html) - formally verified, somewhat optimizing, C compiler, supports most of C99 with some C11 and its own extensions
  * ISAs: x86_32, x86_64, ARMv6 or above, ARM64, RISC-V (32 or 64-bit), PowerPC, PPC64
  * Requires GCC or the proprietary Wind River Diab C Compiler 5, OCaml, and lots of other dependencies
    * It might not be too hard to get rid of the GCC/Diab C dependency by substituting a different assembler and linker
  * License: [proprietary noncommercial license](https://compcert.org/doc/LICENSE.txt)
  * [Commercial license website](https://www.absint.com/compcert/)
  * HN discussions
    * [2011 discussion](https://news.ycombinator.com/item?id=2619650)
    * [2019 discussion](https://news.ycombinator.com/item?id=18968125)
    * [2021 discussion](https://news.ycombinator.com/item?id=27648735)
    * [2024 discussion](https://news.ycombinator.com/item?id=40484190)

## Discussion

* [HN general discussion](https://news.ycombinator.com/item?id=39367523)
* [Benchmarks](https://briancallahan.net/blog/20211010.html)
