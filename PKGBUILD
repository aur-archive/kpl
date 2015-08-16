# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Adam Tenderholt <atenderholt@gmail.com>

pkgname=kpl
pkgver=4.0
pkgrel=1
pkgdesc="An open source plotting program for KDE"
arch=('i686' 'x86_64')
url="http://omnibus.uni-freiburg.de/~stille/kpl/"
license=('GPL')
depends=('kdebase-runtime')
makedepends=('automoc4' 'cmake')
install="${pkgname}.install"
source=("http://omnibus.uni-freiburg.de/~stille/kpl/${pkgname}-${pkgver}.tar.bz2"
        "${pkgname}.patch")
md5sums=('a126e4462267c6f76153b60ebee3745a'
         '4d38c1d63344c106c7c769101c50adff')

build() {
  cd "${srcdir}/${pkgname}"

  # Disable language select because of segfault
  patch -Np1 -i ../${pkgname}.patch

  cmake -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}"
  make DESTDIR="${pkgdir}" install
}
