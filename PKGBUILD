pkgname=tea
pkgver=50.0.1
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://tea.ourproject.org/"
license=('GPL')
depends=('qt5-base' 'poppler-qt5' 'djvulibre' 'zlib')
makedepends=('clang')
optdepends=('aspell' 'hunspell')
source=("https://github.com/psemiletov/tea-qt/archive/${pkgver}.tar.gz")
md5sums=('6d2e2c92c53a2162a1609975cbe29acb')

build() {
  cd "${srcdir}/${pkgname}-qt-${pkgver}"
  qmake-qt5 PREFIX=/usr \
            CONFIG+=usepoppler \
            CONFIG+=usedjvu
  make
}

package(){
  cd "${srcdir}/${pkgname}-qt-${pkgver}"
  make INSTALL_ROOT="${pkgdir}" install
}
