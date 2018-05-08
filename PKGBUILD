# Maintainer: Riccardo Berto <riccardobrt at gmail dot com>

_pkgname=redis-graph
pkgname=$_pkgname-git
pkgver=r215.9db0b8c
pkgrel=1
pkgdesc="This project is a Redis module that implements a graph database."
arch=('i686' 'x86_64')
url="https://github.com/swilly22/$_pkgname"
license=('AGPL-3.0')
depends=('redis')
makedepends=('git')
source=("git+$url")
install=$pkgname.install
sha256sums=("SKIP")

pkgver() {
	cd "$_pkgname"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd $_pkgname/
	make $MAKEFLAGS
}

package() {
        cd $_pkgname
        install -D src/redisgraph.so $pkgdir/usr/lib/redis/redisgraph.so
        install -Dm644 LICENSE $pkgdir/usr/share/licenses/$_pkgname/LICENSE
}
