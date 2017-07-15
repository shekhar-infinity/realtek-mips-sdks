# rlx4xxx-rlx5xxx-toolchain
The Realtek SDK (RSDK) v1.3.6 Lexra toolchain ([R]LX5280, [R]LXxxxx) and a shell source file to set your environment

## What is this

This is a toolchain provided by Realtek that is compatible with the MIPS based Lexra brand CPUs, which don't implement unaligned loads and stores for patent reasons. This chip can be found in older embedded devices. The activate script is for convenience and will set up your environment to use the toolchain after copying it where you want it on your local filesystem

## Using

Using this to build something is pretty straightforward using the activate script in the root of the repository. Just place the activate script into the rsdk-1.5.10-5281-EB-2.6.30-0.9.30-m32ub-130429/ directory and copy the rsdk-1.5.10-5281-EB-2.6.30-0.9.30-m32ub-130429 directory to where you would like it to reside, i.e. /toolchains. At that point, ```source /toolchains/rsdk-1.5.10-5281-EB-2.6.30-0.9.30-m32ub-130429/activate``` and you are all set. You can then build software using ```configure``` style build systems, or via plain old ```gcc```. You should make use of the ```cross_configure``` alias

## Examples

### Use gcc to compile something by hand

```
$ gcc bah.c -o bah 
```

### Use a ```configure``` based build system

```
$ cross_configure
...
$ make -j
```

### You probably want to statically link things

```CFLAGS='-fPIC -static' CXXFLAGS='-fPIC -static``` works fine with *most* configure scripts, or you can obviously do things by hand using ```gcc -fPIC -static bah.c -o bah```

## Other projects utilizing this

Several of my projects use this to produce statically linked executables like gdbserver, lsof and other things useful on embedded devices

* [embedded-toolkit](https://github.com/mzpqnxow/embedded-toolkit)
* [gdb-static-cross](https://github.com/mzpqnxow/gdb-static-cross)

## Caveat Emptor
This is a very old uClibc-0.9.30.3 based toolchain using gcc-4.4.7, so you will certainly run into issues, especially with header files which predate some newer Linux system calls. It is usually trivial to get things to build, see for example the gdb-7.12 patch used in [gdb-static-cross](https://github.com/mzpqnxow/gdb-static-cross/tree/master/rsdk-1.3.6-patch)
