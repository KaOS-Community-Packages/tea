pkgname=tea
pkgver=60.5.0
pkgrel=1
pkgdesc="A Qt-based text editor for Linux and *BSD. With an ultimate small size TEA provides you hundreds of functions."
arch=('x86_64')
url="http://tea.ourproject.org/"
license=('GPL')
depends=('qt6-base' 'qt6-5compat' 'poppler' 'djvulibre' 'zlib' 'aspell' 'hunspell')
source=("https://github.com/psemiletov/tea-qt/archive/${pkgver}.tar.gz")
md5sums=('8078690f84d55040053d22a7f48f56ba')

build() {
	cd "${srcdir}/${pkgname}-qt-${pkgver}"
	mkdir -p build
	cd build
	cmake .. \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_PREFIX_PATH=/usr/lib/qt6 \
		-DUSE_ASPELL=ON \
		-DUSE_HUNSPELL=ON \
		-DUSE_PRINTER=ON \
		-DUSE_PDF=ON \
		-DUSE_DJVU=ON
	make
}

package(){
	cd "${srcdir}/${pkgname}-qt-${pkgver}/build"
	make DESTDIR="${pkgdir}" install
}
