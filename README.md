# realtek-mips-sdks

This package contains various Realtek SDKs (including toolchains) for MIPS based systems. It also includes an 'activate' script that can be sourced from a bash shell. This script makes using the toolchains easier.

## Lexra

Packages in this repository support the relatively obscure and absolutely odd Lexra CPU, which due to patent reasons does not support unaligned (half) loads and stores. There is no support in GCC for this (modern or historic) so it is useful to have on hand if you encounter such a device

## Usage and notes

Where possible, effort was made to avoid duplicate toolchains. Also, in some cases an "activate" script was included for convenience. This file should be placed in the root of the toolchain and ```source```d from a bash shell. It will set things like ```PATH``` as well as other variables like ```CC``` and ```CXX```, etc

## Copyright / License

All code/packages in this repository are copyright of their respective owners. The only code added under copyright is activate scripts, which are copyright copyright@mzpqnxow.com under GPLv2
