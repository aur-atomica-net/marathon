# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=marathon
pkgver=1.0.0.RC1
_dl_pkgver=1.0.0-RC1
pkgrel=1
pkgdesc='Deploy and manage containers (including Docker) on top of Apache Mesos at scale.'
arch=('any')
url='https://mesosphere.github.io/marathon/'
license=('Apache')
depends=('java-environment')
backup=("etc/conf.d/${pkgname}")
source=("${pkgname}-${_dl_pkgver}.tar.gz"::"http://downloads.mesosphere.io/marathon/v${_dl_pkgver}/marathon-${_dl_pkgver}.tgz"
        "${pkgname}.conf"
        "${pkgname}.service")
sha256sums=('b4bf04ffb8555134e53de73784dc57688768e3c14ed3ab1498128cebbc968858'
            '0955bc73f3ca0d5fe2804c29ae52eb61b98c0802dd8558dba585a66f868f353f'
            '3733b6df2ea25b81c4a080261c8da74c86ed617a45f79a73028a1bf729e12a66')

build() {
    cd "${srcdir}/${pkgname}-${_dl_pkgver}"
    ./bin/build-distribution
}

package() {
    mkdir -p ${pkgdir}/usr/lib/systemd/system
    install -m644 ${srcdir}/${pkgname}.service ${pkgdir}/usr/lib/systemd/system

    mkdir -p ${pkgdir}/etc/conf.d
    install -m644 ${srcdir}/${pkgname}.conf ${pkgdir}/etc/conf.d/${pkgname}

    install -Dm644 ${srcdir}/${pkgname}-${_dl_pkgver}/target/marathon-runnable.jar $pkgdir/usr/share/$pkgname/$pkgname.jar
}
