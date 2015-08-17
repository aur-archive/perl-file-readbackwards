# Mantainer: 3ED <krzysztof1987 at gmail dot com>

pkgname=perl-file-readbackwards
_lastauthor=U/UR/URI
_pkgname=File-ReadBackwards
pkgver=1.05
pkgrel=1
pkgdesc="read a file backwards by lines"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl')
makedepends=('perl-extutils-makemaker')
url="http://search.cpan.org/dist/${_pkgname}/"
source=(http://search.cpan.org/CPAN/authors/id/${_lastauthor}/${_pkgname}-${pkgver}.tar.gz)
sha256sums=('82b261af87507cc3e7e66899c457104ebc8d1c09fb85c53f67c1f90f70f18d6e')

build() {
  cd ${_pkgname}-${pkgver}

  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL="--skipdeps" \
    PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'" \
    PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
    MODULEBUILDRC=/dev/null

  perl Makefile.PL
  make
}
check() {
  cd ${_pkgname}-${pkgver}
  make test
}
package() {
  cd ${_pkgname}-${pkgver}
  make install
}

