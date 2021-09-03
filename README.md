# MinGW package for the Fortran package manager

This repository provides package build instructions for the Fortran package manager ([fpm](https://github.com/fortran-lang/fpm)) compatible with the [MSYS2 toolchain](https://msys2.org).

The package build has been submitted to the MinGW repository [MINGW-packages#9481](https://github.com/msys2/MINGW-packages/pull/9481) and is now available in the MSYS2 distribution as [mingw-w64-fpm](https://packages.msys2.org/base/mingw-w64-fpm).
Therefore, this project has been *archived*.

To install fpm use

```
pacman -S mingw-w64-x86_64-fpm
```

For more details on this project visit the [fpm wiki](https://github.com/fortran-lang/fpm/wiki/Packaging-Fpm#msys2-windows).

## License

The package build files are available under a BSD-3-Clause license.
