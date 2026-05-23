# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-night-light
pkgver=6.6.5
pkgrel=1
#_commit="9402eca9b8b38399e24da784a50dc03e51fd4a70"
pkgdesc='Sonic applet for audio volume management using PulseAudio'
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
makedepends=(extra-cmake-modules
             ki18n
             qt6-tools)
groups=(sonicde)
conflicts=(knighttime)
provides=(knighttime)
replaces=(knighttime)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('b055a55571015938a6d3da626552dddd2f86ab2a1ddcc945ae3a3c38b0bed77c')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  rm -r $pkgdir/usr/lib/systemd
}
