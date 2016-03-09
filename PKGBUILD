_pkgname=QuiteRSS
pkgname=quiterss
pkgver=0.18.4
pkgrel=1
pkgdesc="Fast and light RSS/Atom feed reader written on Qt/С++"
arch=('x86_64')
url="http://quiterss.org/"
license=('GPL3')
depends=('qt5-multimedia' 'qt5-webkit' 'hicolor-icon-theme' 'desktop-file-utils')
makedepends=('qt5-tools')
install=$pkgname.install
source=("http://quiterss.org/files/$pkgver/$_pkgname-$pkgver-src.tar.gz")
sha512sums=('effca5c2f187d8eb73838c2668a14bcf64dfd99c2e4a3f2f70fa344e9b74073e588477f74e1f5750d96f8bff7ee765306d5bf91aecd1c2155d60bf0c51e0e3e9')

build() {
cd "$srcdir"
qmake-qt5 "$srcdir/$_pkgname.pro" \
  PREFIX=/usr \
  CONFIG+=LINUX_INTEGRATED \
  DISABLE_PHONON=1 \
  INSTALL_ROOT_PATH="$pkgdir"
make
}
package() {
cd "$srcdir"
make INSTALL_ROOT="$pkgdir" install
}
