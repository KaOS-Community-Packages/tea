pkgname=tea
pkgver=41.0.0
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://semiletov.org/tea/"
license=('GPL')
depends=('qt5-base')
optdepends=('aspell' 'hunspell')
source=(http://semiletov.org/tea/dloads/tea-$pkgver.tar.bz2
        tea.desktop)
md5sums=('36e0504ccfeef676ee04cf41aede33b5'
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
