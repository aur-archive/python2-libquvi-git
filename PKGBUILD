# Maintainer: Tom Vincent <http://tlvince.com/contact/>
pkgname=python2-libquvi-git
pkgver=20111121
pkgrel=2
pkgdesc="LibQuvi wrapper for Python"
arch=(any)
url="https://github.com/metal3d/python-libquvi"
license=('GPL')
depends=('python2' 'libquvi')
makedepends=('git' 'cython2')
options=(!emptydirs)

_gitroot=git://github.com/metal3d/python-libquvi.git
_gitname=$pkgname

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$pkgname"
  python2 setup.py install --root="$pkgdir/" --optimize=1
}

# vim:set ts=2 sw=2 et:
