pkgname="kitchenowl"
pkgver=0.5.0
pkgrel=1
pkgdesc="KitchenOwl is a self-hosted grocery list and recipe manager."
arch=("x86_64")
url="https://github.com/TomBursch/kitchenowl"
license=("GPL3")
source=(
  "kitchenowl.png"
  "kitchenowl.desktop"
  "launcher.sh"
  "${pkgname%}-${pkgver}.tar.gz::https://github.com/TomBursch/kitchenowl/releases/download/v${pkgver}/kitchenowl_Linux.tar.gz"
)
sha256sums=(
  "06f7b7e317e1732feda0bce957af7bf7b8a797147d865951df21532cb949863b"
  "8ec1df01450010aefb23728c69b8ff6eb2d9ceae9e1e1464374c6f0ae36a30c1"
  "15c3bbe7db615abc3745c5d013e0c04b6e47ad48265ecdc077d59dadcdb1bffa"
  "7ccdf4357d2240a0a8dd25c6e769cf3d474e52f6ede585845adc46782d0f2fbb"
)

package() {
  install -d "$pkgdir/opt/${pkgname}"
  cp -r "$srcdir/data" "$pkgdir/opt/${pkgname}/"
  cp -r "$srcdir/lib" "$pkgdir/opt/${pkgname}/"
  cp "$srcdir/kitchenowl" "$pkgdir/opt/${pkgname}/"

  install -Dm644 "${srcdir}/kitchenowl.png" "${pkgdir}/usr/share/icons/kitchenowl.png"
  install -Dm644 "${srcdir}/kitchenowl.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
  install -Dm755 "${srcdir}/launcher.sh" "${pkgdir}/usr/bin/kitchenowl"
}
