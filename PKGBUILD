# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=marathon
pkgver=0.8.2
pkgrel=1
pkgdesc='Deploy and manage containers (including Docker) on top of Apache Mesos at scale.'
arch=('any')
url='https://mesosphere.github.io/marathon/'
license=('Apache')
depends=('java-runtime' 'java-environment')
# makedepends=('sbt')
# Rename to force re-download on new version

source=(
  "${pkgname}-${pkgver}.tar.gz"::"https://downloads.mesosphere.io/marathon/v${pkgver}/marathon-${pkgver}.tgz"
)

sha512sums=('3ad6d4929eee181d4142a70d99d880d62bf56c497b0039a77652210a10d238bc9213bd79cd069d87135a3eedfb188115360228d0d87db915ce21d147b2d2e62e')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./bin/build-distribution
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/marathon-runnable.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
