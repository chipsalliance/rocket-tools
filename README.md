rocket-tools [![Build Status](https://travis-ci.org/chipsalliance/rocket-tools.svg?branch=master)](https://travis-ci.org/chipsalliance/rocket-tools)
===========================================================================

This meta-repository points to a collection of software tools that support
the [Rocket Chip Generator](https://github.com/chipsalliance/rocket-chip),
including:

* [Spike](https://github.com/riscv/riscv-isa-sim/), the ISA simulator
* [riscv-tests](https://github.com/riscv/riscv-tests/), a battery of
ISA-level tests
* [riscv-opcodes](https://github.com/riscv/riscv-opcodes/), the
enumeration of all RISC-V opcodes executable by the simulator
* [riscv-pk](https://github.com/riscv/riscv-pk/), which contains `bbl`,
a boot loader for Linux and similar OS kernels, and `pk`, a proxy kernel that
services system calls for a target-machine application by forwarding them to
the host machine

The above projects are not supported via this repository, and this repository
is not supported for any purpose other than use with Rocket Chip.

Quickstart
----------

	$ git submodule update --init --recursive
	$ export RISCV=/path/to/install/riscv/toolchain
	$ ./build.sh


Ubuntu packages needed:

	$ sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev libusb-1.0-0-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev device-tree-compiler pkg-config libexpat-dev libfl-dev

Fedora packages needed:

	$ sudo dnf install autoconf automake @development-tools curl dtc libmpc-devel mpfr-devel gmp-devel libusb-devel gawk gcc-c++ bison flex texinfo gperf libtool patchutils bc zlib-devel expat-devel flex-devel

_Note:_ This requires a compiler with C++11 support (e.g. GCC >= 4.8).
To use a compiler different than the default, use:

	$ CC=gcc-5 CXX=g++-5 ./build.sh

_Note for OS X:_ We recommend using [Homebrew](https://brew.sh) to install the dependencies (`libusb dtc gawk gnu-sed gmp mpfr libmpc isl wget automake md5sha1sum`) or even to install the tools [directly](https://github.com/riscv/homebrew-riscv). This repo will build with Apple's command-line developer tools (clang) in addition to gcc.
