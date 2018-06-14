# Contributor: Sasha Gerrand <alpine-pkg@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkg@sgerrand.com>
pkgname=kt
pkgver=12.1.0
pkgrel=0
pkgdesc="Kafka tool that loves JSON"
url="https://github.com/fgeller/kt"
arch="all"
license="Unknown"
depends=""
makedepends="go"
install=""
subpackages=""
source="$pkgname-$pkgver.tar.gz::https://github.com/fgeller/$pkgname/archive/v$pkgver.tar.gz"
builddir="$srcdir/go/src/github.com/fgeller/kt"
options="!strip"

prepare() {
	mkdir -p "$srcdir/go/src/github.com/fgeller"
	mv "$srcdir/$pkgname-$pkgver" "$builddir"
}

build() {
	export GOPATH="$srcdir/go"
	cd "$builddir"
	go build -o kt -ldflags "-X main.version=$pkgver" github.com/fgeller/kt || return 1
}

package() {
	cd "$builddir"
	install -sD -m 755 kt "$pkgdir"/usr/bin/kt
}

sha512sums="7a179953522fde167f3bc61352b48066e235b4632ffe1ca982eec47a9a930ddf72116d7e2a5f4d7386637829489dd9488ccbaa159a467a0516b24196a2ffa9ea  kt-12.1.0.tar.gz"
