# $Id: PKGBUILD 49034 2011-06-09 21:26:14Z andrea $
# Maintainer: Angel Velasquez <angvp@archlinux.org>
# Maintainer: Juergen Hoetzel <juergen@archlinux.org>

pkgname=libfm
pkgver=0.1.16
pkgrel=1
pkgdesc="the core of next generation file manager PCManFM"
url="http://pcmanfm.sourceforge.net/"
arch=('i686' 'x86_64')
license=('GPL')
groups=('lxde')
options=('!libtool')
install=libfm.install
depends=('gtk2' 'menu-cache' 'shared-mime-info' 'udisks')
source=(http://downloads.sourceforge.net/pcmanfm/$pkgname-$pkgver.tar.gz)
md5sums=('c09bce415ff6dc2dd835e28aeddeabe3')

build() {
  cd $srcdir/$pkgname-$pkgver
  sed -i -e "s|docs/Makefile docs/reference/Makefile docs/reference/libfm/Makefile ||" configure
  ./configure --prefix=/usr \
    --sysconfdir=/etc \
    --enable-udisks \
    --with-gnu-ld 
  make 
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}
