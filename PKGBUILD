# Maintainer: strigyskow
pkgname=spatialite_gui
pkgver=1.5.0
_pkgver=1.5.0-stable
pkgrel=4
pkgdesc="spatialite-gui is an open source Graphical User Interface (GUI) tool supporting SpatiaLite."
url="https://www.gaia-gis.it/fossil/spatialite_gui/index"
arch=('x86_64' 'i686')
license=('GPLv3')
depends=(libspatialite libgaiagraphics wxgtk)
optdepends=()
makedepends=()
conflicts=()
replaces=()
backup=()
#install='foo.install'
source=("http://www.gaia-gis.it/gaia-sins/spatialite-gui-sources/spatialite_gui-${_pkgver}.tar.gz")
md5sums=('0b2f8eb95392ddcd8993787578c6e45f')

build() {
  cd "${srcdir}/${pkgname}-${_pkgver}"
  ./configure --prefix="/usr"
  make
  make check
}

package() {
  cd "${srcdir}/${pkgname}-${_pkgver}"
  make DESTDIR="${pkgdir}" install
  install -D -m644 gnome_resource/spatialite-gui.desktop "${pkgdir}"/usr/share/applications/spatialite-gui.desktop
  install -D -m644 gnome_resource/spatialite-gui.png "${pkgdir}"/usr/share/pixmaps/spatialite-gui.png
}

# vim:set ts=2 sw=2 et:
