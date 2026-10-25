# Maintainer: Ian

pkgname=dmenu-patched
pkgver=5.4
pkgrel=1
pkgdesc="Dynamic menu for X, patched with runtime X Resources support"
arch=('x86_64')
url="https://tools.suckless.org/dmenu/"
license=('MIT')
depends=('libxinerama' 'libxft' 'freetype2' 'fontconfig')
makedepends=('libxft')
provides=('dmenu')
conflicts=('dmenu')
source=("https://dl.suckless.org/tools/dmenu-${pkgver}.tar.gz"
        "dmenu-xresources-20260510-7175c48.diff::https://tools.suckless.org/dmenu/patches/xresources/dmenu-xresources-20260510-7175c48.diff")
sha256sums=('8fbace2a0847aa80fe861066b118252dcc7b4ca0a0a8f3a93af02da8fb6cd453'
            '2ec06173fce7bf3d4b34f3d573b65630f70c2b97d876e0d999aab2943a7d7077')

prepare() {
	cd "dmenu-${pkgver}"
	patch -p1 < "${srcdir}/dmenu-xresources-20260510-7175c48.diff"
}

build() {
	cd "dmenu-${pkgver}"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "dmenu-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
