# Contributor: Christopher Bayliss <christopher.j.bayliss@gmail.com>
pkgname=xiphos-gtk3
pkgver="4.0.2"
pkgrel=3
pkgdesc="A Bible study tool - This version is built to use GTK3 and WebKit2GTK+."
arch=('i686' 'x86_64')
url="http://xiphos.org"
license=('GPL')
depends=('webkit2gtk' 'libgsf' 'gconf' 'sword' 'biblesync' 'gtkhtml4' 'festival')
makedepends=('gnome-common' 'gnome-doc-utils' 'intltool' 'subversion')
provides=('gnomesword' 'xiphos' 'xiphos-svn')
conflicts=('gnomesword' 'xiphos' 'xiphos-svn')
install=xiphos-gtk3.install
source=('http://downloads.sourceforge.net/project/gnomesword/Xiphos/4.0.2/xiphos-4.0.2-20150415.tar.gz')
md5sums=('d5151d06bc701c82f9a1fa7f81214fe1')

build() {
  cd "$srcdir/xiphos-$pkgver"
  CXX=g++ python2 ./waf --prefix=/usr --gtk=3 configure 
  python2 ./waf --prefix=/usr --gtk=3 build 
}

package() {
  cd "$srcdir/xiphos-$pkgver"
  python2 ./waf --destdir=$pkgdir --no-post-install install 
}
