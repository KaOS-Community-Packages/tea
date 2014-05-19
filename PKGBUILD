# Maintainer:

pkgname=tea
pkgver=37.2.1
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://semiletov.org/tea/"
license=('GPL')
depends=('qt5-base')
optdepends=('aspell' 'hunspell')
source=(http://semiletov.org/tea/dloads/tea-$pkgver.tar.bz2
        tea.desktop)
md5sums=('a74c2d18cc2cace9d961d1a215b19e31'
         '377ace3363124f4c086de0babb820761')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i 's|i + j|(int)(i + j)|' textproc.cpp
  qmake-qt5 PREFIX=/usr/bin
  make
}

package(){
  cd "${srcdir}/${pkgname}-${pkgver}"
  make INSTALL_ROOT="${pkgdir}" install
  install -Dm644 "${srcdir}/tea.desktop" "${pkgdir}/usr/share/applications/tea.desktop"
  install -Dm644 icons/tea_icon_v2.png "${pkgdir}/usr/share/pixmaps/tea.png"
}
