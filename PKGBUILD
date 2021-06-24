_realname=fpm
pkgbase=mingw-w64-${_realname}
pkgname="${MINGW_PACKAGE_PREFIX}-${_realname}"
pkgver=0.3.0
pkgrel=1
arch=('any')
pkgdesc="Fortran package manager (mingw-w64)"
url="https://github.com/fortran-lang/fpm"
depends=("${MINGW_PACKAGE_PREFIX}-gcc-libs" "${MINGW_PACKAGE_PREFIX}-gcc-libgfortran")
makedepends=("${MINGW_PACKAGE_PREFIX}-gcc-fortran")
options=('strip')
license=('MIT')
source=(${_realname}-${pkgver}.F90::"https://github.com/fortran-lang/fpm/releases/download/v${pkgver}/${_realname}-${pkgver}.F90")
sha256sums=('a0670253a27a8b3745e694279d1c5feacbb111a932537c5932edde0c0f3ffa8b')
noextract=("${_realname}-${pkgver}.f90")

build() {
  cd "${srcdir}"
  local _build="build_${CARCH}"
  local _fc="${MINGW_PREFIX}/bin/gfortran"
  # Compiler flags need some tweaking
  local _fflags="-g -fbacktrace -O3 -J ${_build}"

  mkdir -p "${_build}"
  ${_fc} ${_fflags} "fpm-${pkgver}.F90" -o "${_build}/fpm"
}

package() {
  cd "${srcdir}/build_${CARCH}"
  install -Dm755 fpm "${pkgdir}"${MINGW_PREFIX}/bin/fpm
}
