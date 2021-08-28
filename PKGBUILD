_realname=fpm
pkgbase=mingw-w64-${_realname}
pkgname="${MINGW_PACKAGE_PREFIX}-${_realname}"
pkgver=0.4.0
pkgrel=1
arch=('any')
pkgdesc="Fortran package manager (mingw-w64)"
url="https://github.com/fortran-lang/fpm"
depends=("${MINGW_PACKAGE_PREFIX}-gcc-libs" "${MINGW_PACKAGE_PREFIX}-gcc-libgfortran" "git")
makedepends=("${MINGW_PACKAGE_PREFIX}-gcc-fortran" "${MINGW_PACKAGE_PREFIX}-curl")
options=('strip')
license=('MIT')
source=(${_realname}-${pkgver}.tar.gz::"https://github.com/fortran-lang/fpm/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('6c1574273164f859591547b7aae3b2d39471cf8a1d901cf1e453e607fbe9757a')

build() {
  cd "${srcdir}/${_realname}-${pkgver}"
  local _build="build_${CARCH}"
  local _fc="${MINGW_PREFIX}/bin/gfortran"

  FC="${_fc}" ./install.sh --prefix="${_build}"
}

package() {
  cd "${srcdir}/${_realname}-${pkgver}/build_${CARCH}"
  install -Dm755 bin/fpm "${pkgdir}"${MINGW_PREFIX}/bin/fpm
}
