# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>

pkgname=sonic-night-light
pkgver=6.7.1
pkgrel=1
pkgdesc='Helpers for scheduling the dark-light cycle'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-night-light'
license=(LGPL)
depends=(gcc-libs
         glibc
         kconfig
         kdbusaddons
         kholidays
         qt6-base
         qt6-positioning
         sonic-frameworks-core-addons)
makedepends=(ki18n
             qt6-tools
             sonic-frameworks-cmake-modules)
provides=(knighttime)
conflicts=(knighttime)
groups=(sonicde)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('e4d9ffe2948291a904efb29b0abb9b7350485e8c7b2e3c14d00f9f44cd68056f')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_LIBEXECDIR=lib
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
