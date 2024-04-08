# Mantainer: sgar < swhaat at github >

pkgname=python-aioesphomeapi
pkgver=23.1.1
pkgrel=1
pkgdesc="Python Client for ESPHome native API. Used by Home Assistant."
url="https://github.com/esphome/aioesphomeapi"
depends=('python-setuptools'
    'python-cryptography'
    'python-protobuf'
    'python-zeroconf'
    'python-chacha20poly1305-reuseable'
    'python-noiseprotocol-git'
    'python-aiohappyeyeballs')
license=('MIT')
arch=('any')
source=("https://github.com/esphome/aioesphomeapi/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('2348220e0d83571ccd69abcdef4631279509d6e616345621c4e0cf0d104d7435')

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
