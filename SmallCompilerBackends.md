# Small compiler backends

These are compiler backends that can be used for many compilers, not just for a single language, kind of like LLVM. They should be rather small.

## Small compiler backends

* [QBE](https://c9x.me/compile/)
  * ISAs: amd64, arm64, riscv64
  * Target OSes: GNU/Linux, OS X
  * Written in C99
  * Discussions:
    * [Reddit 2016](https://libreddit.bus-hit.me/r/programming/comments/4fysrk/qbe_my_homegrown_simple_compiler_backend/)
    * [HN 2016](https://news.ycombinator.com/item?id=11555527)
    * [HN 2020](https://news.ycombinator.com/item?id=25273907)
    * [HN 2024](https://news.ycombinator.com/item?id=40346320)
* [libFirm](https://libfirm.github.io/index.html)
  * ISAs (mature): x86_32, SPARC
  * ISAs (experimental): x86_64, ARM
  * Written in C99
  * Discussions:
    * [Reddit 2017](https://libreddit.bus-hit.me/r/programming/comments/5majpy/an_alternative_to_llvm_libfirm/)
* [Amsterdam Compiler Kit](https://tack.sourceforge.net/)
  * ISAs (well supported): i86, i386, 68000, i80, and VideoCore IV
  * ISAs (experimental): 6500, ARM, i80, Z80, Z8000, i86, i386, 68000, 68020, NS32016, SPARC, VAX4, PDP11 and VideoCore IV
  * Includes assembler and linker
  * Platforms: pc86, linux386, linux68k, linuxppc, linuxmips, cpm, rpi (VideoCore IV), pdpv7, msdos86 and msdos386
  * Frontends: ANSI C, B, Pascal and Modula-2
  * Written in C90
* [TenDRA](http://www.tendra.org/)
  * ISAs: alpha, hppa, m68k, MIPS, PowerPC, SPARC, x86_32
  * See [trans(1)](http://www.tendra.org/trans.1/) for supported ABIs
* [ELVM](https://github.com/shinh/elvm) - transpiles to many esoteric languages

## Small compiler backends written in large languages

* Eigen Compiler Suite
  * Still small, but it's written in C++17 which needs multiple stages of large compilers (multiple versions of gcc) to bootstrap
* cranelift
  * Also small, but requires Rust which is hard to bootstrap and only has one large compiler

## Larger compiler backends

* LLVM
