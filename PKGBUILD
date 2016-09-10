pkgname=peek
pkgver=0.7.2
pkgrel=1
pkgdesc="An Animated GIF Recorder"
arch=('x86_64')
url="https://github.com/phw/peek"
license=('GPL3')
depends=('gtk3' 'ffmpeg' 'imagemagick')
makedepends=('cmake' 'vala' 'gettext')
source=("git+https://github.com/phw/peek.git#tag=v${pkgver}")
md5sums=('SKIP')

build() {
  cd "${srcdir}/peek"
  cmake -DCMAKE_INSTALL_PREFIX=/usr \
    -DGSETTINGS_COMPILE=OFF
    make
}

package() {
  cd "${srcdir}"/peek
    make DESTDIR="$pkgdir" install
}
