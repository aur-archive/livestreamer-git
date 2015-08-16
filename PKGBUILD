#Maintainer: Daniel Wallace <danielwallace at gtmanfred dot com>
pkgname=livestreamer-git
_pkgname=livestreamer
pkgver=1.12.2.1.g4e69a11
pkgver(){
  cd $_pkgname
  git describe --tags --long | sed 's/-/./g;s/^v//'
}
epoch=1
pkgrel=1
pkgdesc="CLI program that helps launch various streaming services in a real player instead of flash."
arch=('i686' 'x86_64')
url="https://github.com/chrippa/livestreamer" 
license=('GPL3')
depends=('python' 'rtmpdump' 'python-setuptools' 'python-requests')
makedepends=('git' )
conflicts=(livestreamer)

source=("$_pkgname::git://github.com/chrippa/livestreamer.git#branch=develop")
md5sums=('SKIP')

build() {
  cd "$srcdir/$_pkgname"
  python3 setup.py build
}
package(){
  cd "$srcdir/$_pkgname"
  python3 setup.py install --root="$pkgdir/" --optimize=1
}

# vim:set ts=2 sw=2 et:
