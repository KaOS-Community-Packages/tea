pkgname=tea
pkgver=50.0.4
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://tea.ourproject.org/"
license=('GPL')
depends=('qt5-base' 'poppler-qt5' 'djvulibre' 'zlib')
makedepends=('clang')
optdepends=('aspell' 'hunspell')
source=("https://github.com/psemiletov/tea-qt/archive/${pkgver}.tar.gz")
md5sums=('bd713fc3e3086b04175ccb00622616f9')

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
