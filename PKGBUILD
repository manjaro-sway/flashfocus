# Maintainer AUR :     Fenner Macrae <fmacrae.dev at gmail dot com>
# Maintainer Manjaro : Simon Büeler <simon.bueeler at icloud dot com>

pkgname=flashfocus
pkgrel=3
pkgver=2.2.2
pkgdesc="Simple Xorg window focus animations for tiling window managers"
url="https://www.github.com/fennerm/flashfocus"
depends=('python-xcffib'
         'python-click'
         'python-xpybutil'
         'python-marshmallow'
         'python-yaml'
         'python-i3ipc')
makedepends=('python-setuptools')
conflicts=('flashfocus')
provides=('flashfocus')
license=('MIT')
arch=('any')
source=("$pkgname-$pkgver.tar.gz::https://github.com/fennerm/${pkgname}/archive/v${pkgver}.tar.gz")
md5sums=("SKIP")

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    python setup.py build
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm644 flashfocus.service "${pkgdir}/usr/lib/systemd/user/flashfocus.service"
}
