# $Id: PKGBUILD 226486 2014-11-19 17:34:14Z fyan $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdebindings-kimono
pkgver=4.14.3
pkgrel=1
pkgdesc=".NET/Mono bindings for the KDE libraries"
url="https://projects.kde.org/projects/kde/kdebindings/csharp/kimono"
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kdebindings')
depends=('kdebindings-qyoto' 'kdebindings-smokekde')
makedepends=('cmake' 'automoc4' 'kdebindings-smokegen' 'boost' 'kdepimlibs')
optdepends=('kdepimlibs: akonadi bindings')
conflicts=('kdebindings-csharp')
source=("http://download.kde.org/stable/${pkgver}/src/kimono-${pkgver}.tar.xz")
sha1sums=('1d53447eb3c9953c382dbfb9c96abfeaedf67121')

build() {
  cd "${srcdir}"
  mkdir build
  cd build
  cmake ../kimono-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DKDE4_BUILD_TESTS=OFF \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DWITH_Soprano=OFF
  make
}

package() {
  cd "${srcdir}"/build
  make DESTDIR="${pkgdir}" install
}
