# Mantainer: sgar < swhaat at github >

pkgname=python-aioesphomeapi
pkgver=23.2.0
pkgrel=1
pkgdesc="Python Client for ESPHome native API. Used by Home Assistant."
url="https://github.com/esphome/aioesphomeapi"
depends=('python-setuptools'
    'python-aiohappyeyeballs'
    'python-async_interrupt'
    'python-protobuf'
    'python-zeroconf'
    'python-chacha20poly1305-reuseable'
    'python-cryptography'
    'python-noiseprotocol-git'
)
license=('MIT')
arch=('any')
source=("https://github.com/esphome/aioesphomeapi/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('a11fdab02d4bc15af152af26271eeda1845626452a676807997f83ecbda64496')

prepare() {
    cd "$srcdir/aioesphomeapi-${pkgver}"
    sed -i 's/==.*//' requirements.txt
}

build() {
    cd "$srcdir/aioesphomeapi-${pkgver}"
    python setup.py build
}

package() {
    cd "$srcdir/aioesphomeapi-${pkgver}"
    python setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
