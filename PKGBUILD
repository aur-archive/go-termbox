# Maintainer: Alexander Rødseth <rodseth@gmail.com>

pkgname=go-termbox
pkgver=1
pkgrel=3
pkgdesc="Termbox for Go"
arch=('x86_64' 'i686')
url="http://github.com/nsf/termbox-go/"
license=('MIT')
makedepends=('go' 'git')
options=('!strip' '!emptydirs')
_gourl=github.com/nsf/termbox-go

build() {
  cd "$srcdir"
  GOPATH="$srcdir" go get -v -x ${_gourl}/...
}

check() {
  GOPATH="$srcdir" go test -v -x ${_gourl}/...
}

package() {
  source /etc/profile.d/go.sh
  mkdir -p "${pkgdir}/$GOPATH"
  cp -Rv --preserve=timestamps ${srcdir}/{src,pkg} "${pkgdir}/$GOPATH"
}

# vim:set ts=2 sw=2 et:
