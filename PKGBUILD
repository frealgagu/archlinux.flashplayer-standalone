# Maintainer: whike <sebastian.tauch@aborium.com>
 
pkgname=flashplayer-standalone
pkgver=11.2.202.577
pkgrel=1
pkgdesc="Macromedia standalone flash player (nonfree)"
arch=(i686 x86_64)
url=http://www.adobe.com/support/flashplayer/downloads.html
license=(custom)
# License matrix: http://www.adobe.com/products/eulas/
depends=(desktop-file-utils lib32-curl lib32-gtk2 lib32-libxt lib32-nss)
makedepends_x86_64=()
[[ $CARCH == "i686" ]] && depends=(${depends[@]/lib32-/})
options=(!strip)
install=$pkgname.install
source=(http://fpdownload.macromedia.com/pub/flashplayer/updaters/11/flashplayer_11_sa.i386.tar.gz
    license.pdf::http://www.adobe.com/products/eulas/pdfs/PlatformClients_PC_WWEULA-MULTI-20110809_1357.pdf
    flashplayer.desktop)
sha512sums=('e37b3f4a0dd191262e1d10e82707802c3ca23c13f1588acbd4664eecf933d7428fd4af8ced99db3e4175fef1e6375c6b52928fba733f251370c4a5a121a73312'
    'a70fd7127f0f9d64f2c872d1e4634d93e24fdea165abfbe20724e68c1b7297df46362cb449b5a78d0eb4a68e43426965359ca93fd4ba4848d2542e5505bcd2fe'
    'e4139b265896ebd276b4c7931d5718db7ac8b25e5e86decb2161c94d2b6b410dc7160667cda3a330ece40e64e7809d7afc5ddcc94e09352e84359fa4c7fe3e2d')
 
package() {
    desktop-file-install flashplayer.desktop --dir "$pkgdir"/usr/share/applications/
    install -Dm644 license.pdf "$pkgdir"/usr/share/licenses/$pkgname/license.pdf
    install -Dm755 flashplayer "$pkgdir"/usr/bin/flashplayer
}
