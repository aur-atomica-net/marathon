# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=marathon
pkgver=1.0.0.RC1
_dl_pkgver=1.0.0-RC1
pkgrel=1
pkgdesc='Deploy and manage containers (including Docker) on top of Apache Mesos at scale.'
arch=('any')
url='https://mesosphere.github.io/marathon/'
license=('Apache')
depends=('java-runtime' 'java-environment')
source=(
  "${pkgname}-${pkgver}.tar.gz"::"http://downloads.mesosphere.io/marathon/v${_dl_pkgver}/marathon-${_dl_pkgver}.tgz"
)
sha256sums=('b4bf04ffb8555134e53de73784dc57688768e3c14ed3ab1498128cebbc968858')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./bin/build-distribution
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/marathon-runnable.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
