# realtek-mips-sdks

This package contains various Realtek SDKs (including toolchains) for MIPS based systems. It also includes an 'activate' script that can be sourced from a bash shell. This script makes using the toolchains easier.

## Lexra

Packages in this repository support the relatively obscure and absolutely odd Lexra CPU, which due to patent reasons does not support unaligned (half) loads and stores. There is no support in GCC for this (modern or historic) so it is useful to have on hand if you encounter such a device
