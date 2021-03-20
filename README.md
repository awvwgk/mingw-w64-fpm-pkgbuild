# MinGW package for the Fortran package manager

This repository provides package build instructions for the Fortran package manager ([fpm](https://github.com/fortran-lang/fpm)) compatible with the [MSYS2 toolchain](https://msys2.org).

You can install *fpm* by using `makepkg-mingw`

```
git clone https://github.com/awvwgk/mingw-w64-fpm-pkgbuild
cd mingw-w64-fpm
pacman -S base-devel mingw-w64-x86_64-toolchain
MINGW_INSTALLS=mingw64 makepkg-mingw --syncdeps --cleanbuild --log --force
pacman -U mingw-w64-x86_64-fpm-*-any.pkg.tar.zst
```

Alternatively, this project provides prebuild MinGW packages at the [release page](https://github.com/awvwgk/mingw-w64-fpm-pkgbuild/releases/latest).
You can use the prebuild *fpm* package with

```
wget https://github.com/awvwgk/mingw-w64-fpm-pkgbuild/releases/download/current/mingw-w64-x86_64-fpm-0.1.4-1-any.pkg.tar.zst
pacman -U mingw-w64-x86_64-fpm-*-any.pkg.tar.zst
```

## License

The package build files are available under a BSD-3-Clause license.
