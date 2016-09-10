pkgname=tea
pkgver=43.0.0
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://tea.ourproject.org/"
license=('GPL')
depends=('qt5-base' 'poppler-qt5' 'djvulibre')
optdepends=('aspell' 'hunspell')
source=(${url}dloads/tea-$pkgver.tar.bz2
        tea.desktop)
md5sums=('a6e993706e38c70b11975c3801605ce7'
         '377ace3363124f4c086de0babb820761')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i 's|i + j|(int)(i + j)|' textproc.cpp
  qmake-qt5 PREFIX=/usr/bin \
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
