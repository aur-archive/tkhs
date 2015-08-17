# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=tkhs
pkgname=tkhs
pkgver=0.2.3
pkgrel=3
pkgdesc="Simple Presentation Utility"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-mtl' 'haskell-parsec=2.1.0.1' 'haskell-pretty=1.0.1.1' 'haskell-utf8-string' 'haskell-vty<4.2.2')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('bd6d764e03219c046ff909a2adcf99d4')
