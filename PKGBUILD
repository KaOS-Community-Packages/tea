pkgname=tea
pkgver=47.0.0
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://tea.ourproject.org/"
license=('GPL')
depends=('qt5-base' 'poppler-qt5' 'djvulibre' 'zlib')
makedepends=('clang')
optdepends=('aspell' 'hunspell')
source=(${url}dloads/tea-$pkgver.tar.bz2
        tea.desktop)
md5sums=('a7e50a0de413652d70a32ab906be4288'
         '377ace3363124f4c086de0babb820761')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  qmake-qt5 PREFIX=/usr \
            CONFIG+=usepoppler \
            CONFIG+=usedjvu
  make
}

package(){
  cd "${srcdir}/${pkgname}-${pkgver}"
  make INSTALL_ROOT="${pkgdir}" install
  install -Dm644 "${srcdir}/tea.desktop" "${pkgdir}/usr/share/applications/tea.desktop"
  install -Dm644 icons/tea_icon_v2.png "${pkgdir}/usr/share/pixmaps/tea.png"
}
