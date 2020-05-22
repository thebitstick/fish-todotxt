# Maintainer: TheBitStick <the at bitstick dot rip>
pkgname=fish-todotxt-git
_pkgname=fish-todotxt
pkgver=r11.7d25cd4
pkgrel=1
pkgdesc="Simple todo.txt implementation without projects or contexts"
arch=('any')
url="https://github.com/thebitstick/fish-todotxt"
license=('GPL3')
depends=('fish')
makedepends=('git')
provides=('fish-todotxt')
conflicts=('fish-todotxt')
source=('git+https://github.com/thebitstick/fish-todotxt')
sha512sums=('SKIP')

pkgver() {
	cd ${_pkgname}
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
	install -D -t "$pkgdir/usr/bin" "${_pkgname}/todo.fish"
	mv "$pkgdir/usr/bin/todo.fish" "$pkgdir/usr/bin/todo"
} 
