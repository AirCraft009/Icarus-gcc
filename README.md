## Icarus-GCC
A gcc cross-compiler for the Icarus operating system.


### Instructions

- Clone:
  - git clone --config core.autocrlf=false https://github.com/AirCraft009/Icarus-gcc/
  - to a linux env (wsl or native)
  - crlf will break this
- Build:
  - export PREFIX="$HOME/opt/icarus-cross"
  - export TARGET=x86_64-icarus
  - mkdir build-binutils && cd build-binutils
    - make the build dir in parallel w/ src; example:
    - cross
      - build
      - Icarus-gcc
  - ../binutils-gdb/configure --target=\$TARGET --prefix=$PREFIX --with-sysroot --disable-nls --disable-werror
  - sudo make -j$(nproc) && sudo make install