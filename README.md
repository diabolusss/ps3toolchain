[![License](https://img.shields.io/github/license/ps3dev/ps3toolchain.svg)](./LICENSE)

  What does this do?
 ====================

  This program will automatically build and install a compiler and other
  tools used in the creation of homebrew software for the Sony PlayStation 3
  videogame system.

  How do I use it?
 ==================

 1) Set up your environment by installing the following software:

  autoconf, automake, bison, flex, gcc, libelf, make, makeinfo,
  ncurses, patch, python, subversion, wget, zlib, libtool, python,
  bzip2, gmp, pkg-config, g++, libssl-dev, clang

## Linux

  Specifically on debian-based systems, the following command line should
  be enough to install everything necessary:

```bash
  apt-get install autoconf automake bison flex gcc libelf-dev make \
    texinfo libncurses5-dev patch python subversion wget zlib1g-dev \
    libtool libtool-bin python-dev bzip2 libgmp3-dev pkg-config g++ libssl-dev clang
```

  Check [here](https://gist.github.com/diabolusss/61733b0140db2a79e8643038b7b0e12b#file-old_python_install-sh) python2.7 install notes and logs for Arch linux via yay.

## macOS

  On macOS systems, if you have [Homebrew](http://brew.sh) package manager, the following command line should
  be enough to install everything necessary:

```bash
brew install autoconf automake openssl libelf ncurses zlib gmp wget pkg-config
```

 2) Add the following to your login script:
```bash
 sudo mkdir /usr/local/ps3dev
 sudo chown your_user:user_group /usr/local/ps3dev
 
  export PS3DEV=/usr/local/ps3dev
  export PSL1GHT=$PS3DEV

  export PATH=$PATH:$PS3DEV/bin
  export PATH=$PATH:$PS3DEV/ppu/bin
  export PATH=$PATH:$PS3DEV/spu/bin
```

 3) Run the toolchain script (as user):
```bash
  ./toolchain-sudo.sh
```

If everything goes well you'll see such notice:
```
Libraries have been installed in:
   /usr/local/ps3dev/portlibs/ppu/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
```
