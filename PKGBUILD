# Maintainer: Alessio Sergi <asergi at archlinux dot us>

pkgname=gdk-pixbuf-xcf
pkgver=66.b037c59
pkgrel=1
pkgdesc="A GdkPixbuf loader for the XCF (The Gimp) file format"
arch=('i686' 'x86_64')
url="http://gitorious.org/xcf-pixbuf-loader"
license=('LGPL2.1')
depends=('bzip2' 'gdk-pixbuf2')
makedepends=('git')
options=('!libtool')
install=$pkgname.install
source=("$pkgname::git://gitorious.org/xcf-pixbuf-loader/mainline.git")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  echo $(git rev-list --count master).$(git rev-parse --short master)
}

build() {
  cd "$pkgname"
  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "$pkgname"
  install -d -m 755 "$pkgdir"/usr/lib/gdk-pixbuf-2.0/2.10.0/loaders
  install -m 644 .libs/libioxcf.so "$pkgdir"/usr/lib/gdk-pixbuf-2.0/2.10.0/loaders/
}
