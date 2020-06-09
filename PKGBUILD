pkgname=peek
pkgver=1.5.1
pkgrel=2
pkgdesc="An Animated GIF Recorder"
arch=('x86_64')
url="https://github.com/phw/peek"
license=('GPL3')
depends=('gtk3' 'ffmpeg' 'imagemagick')
makedepends=('meson' 'vala' 'gettext' 'ninja')
source=("https://github.com/phw/peek/archive/${pkgver}.tar.gz")
md5sums=('SKIP')

build() {
  mkdir -p $srcdir/$pkgname/build
  cd $srcdir/$pkgname/build

  meson setup \
	--prefix		/usr \
	--libexecdir	lib \
	--sbindir		bin \
	--buildtype		plain \
	--auto-features	enabled \
	--wrap-mode		nodownload \
	-D				b_lto=true \
	-D				b_pie=true \
	..

  ninja
}

package() {
  cd $srcdir/$pkgname/build

  DESTDIR="$pkgdir" ninja install
}
