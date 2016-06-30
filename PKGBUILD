pkgname=go-bin
pkgver=1.6.2
pkgrel=1
provides=('go' 'go-tools')
conflicts=('go' 'go-tools')
pkgdesc='Compiler and tools for the Go programming language from Google'
arch=('x86_64' 'i686')
url='http://golang.org/'
license=('BSD')
makedepends=('git')
options=('!strip' 'staticlibs')

md5sums_x86_64=('ebfb8b38330c8779b121c43433c4b9be')
md5sums_i686=('c299bcd9571fbcbd862131004d6552e2')

source_i686=("https://storage.googleapis.com/golang/go${pkgver}.linux-386.tar.gz")
source_x86_64=("https://storage.googleapis.com/golang/go${pkgver}.linux-amd64.tar.gz")

package() {
	mkdir -p $pkgdir/usr/lib
	tar -C $pkgdir/usr/lib -xzf go${pkgver}.linux-*.tar.gz

	# bin
	mkdir -p $pkgdir/etc/profile.d
	cat > $pkgdir/etc/profile.d/go-bin.sh <<-'EOF'
	#!/bin/sh

	export PATH=$PATH:/usr/lib/go/bin
	EOF
}
