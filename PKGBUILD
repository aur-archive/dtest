# Maintainer:  Atila Neves
pkgname=dtest
pkgver=0.2.6
pkgrel=1
pkgdesc="Utility to run unit-threaded unit tests for the D programming language"
arch=('i686' 'x86_64')
url="https://github.com/atilaneves/dtest"
license=('BSD')
makedepends=('d-compiler' 'd-stdlib' 'git')
depends=('d-compiler' 'd-runtime')
conflicts=()
source=(
    "git+http://github.com/atilaneves/dtest.git#tag=v$pkgver"
    "git+https://github.com/Dicebot/Arch-PKGBUILDs.git"
)
sha256sums=(
    'SKIP'
    'SKIP'
)

build()
{
  DMD=`$srcdir/Arch-PKGBUILDs/d-compiler.sh`
  cd "${srcdir}/${pkgname}"

  $DMD -O -release -inline dtest.d
}

package()
{
  cd "${srcdir}/${pkgname}"
  install -D -m755 dtest "${pkgdir}/usr/bin/dtest"
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
