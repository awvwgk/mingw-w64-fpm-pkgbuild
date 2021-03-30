_realname=fpm
pkgbase=mingw-w64-${_realname}
pkgname="${MINGW_PACKAGE_PREFIX}-${_realname}"
pkgver=0.2.0
pkgrel=1
arch=('any')
pkgdesc="Fortran package manager (mingw-w64)"
url="https://github.com/fortran-lang/fpm"
depends=("${MINGW_PACKAGE_PREFIX}-gcc-libs" "${MINGW_PACKAGE_PREFIX}-gcc-libgfortran")
makedepends=("${MINGW_PACKAGE_PREFIX}-gcc-fortran")
options=('strip')
license=('MIT')
source=(${_realname}-${pkgver}.f90::"https://github.com/fortran-lang/fpm/releases/download/v${pkgver}/${_realname}-${pkgver}.f90")
sha256sums=('79d5041f5cebd1adff999017b3b5f88d8814267dbd0faaa0f7c720411ede463e')
noextract=("${_realname}-${pkgver}.f90")

build() {
  cd "${srcdir}"
  local _build="build_${CARCH}"
  local _fc="${MINGW_PREFIX}/bin/gfortran"
  # Compiler flags need some tweaking
  local _fflags="-J ${_build}"

  mkdir -p "${_build}"
  ${_fc} ${_fflags} "fpm-${pkgver}.f90" -o "${_build}/fpm"
}

package() {
  cd "${srcdir}/build_${CARCH}"
  install -Dm755 fpm "${pkgdir}"${MINGW_PREFIX}/bin/fpm
}
