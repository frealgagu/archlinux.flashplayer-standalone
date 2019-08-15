# Maintainer: Fredy García <frealgagu at gmail dot com>
# Maintainer: Omar Pakker <archlinux@opakker.nl>
# Contributor: boosterdev@linuxmail.org

pkgname=flashplayer-standalone
pkgver=32.0.0.238
pkgrel=1
pkgdesc="Adobe Flash Player Standalone (A.K.A. Adobe Flash Player Projector)"
arch=("x86_64")
url="http://www.adobe.com/support/${pkgname%-standalone}/downloads.html"
license=("custom:ADOBE" "LGPL")
depends=("gtk2" "libgl" "nss")
optdepends=('alsa-lib: for sound through alsa')
makedepends=("gendesk")
options=(!strip)
source=("${pkgname}-${pkgver}.tar.gz::https://fpdownload.macromedia.com/pub/${pkgname%-standalone}/updaters/${pkgver%%.*}/flash_player_sa_linux.${arch}.tar.gz")
sha256sums=("c0836e94058fa1640888619e5122ed7b0dbaefe72244b18aec5b2b29622fa92a")

prepare() {
  cd "${srcdir}"
  gendesk -f -n \
    --pkgname "${pkgname}" \
    --pkgdesc "${pkgdesc}" \
    --name "Adobe Flash Player Standalone" \
    --genericname "Flash Player" \
    --comment "Player for using content created on the Adobe Flash platform" \
    --exec "/usr/bin/${pkgname%-standalone}" \
    --categories "Audio;AudioVideo;Graphics;GTK;Player;Video;Viewer" \
    --mimetypes "application/x-shockwave-flash;image/gif;image/jpg;image/png"
}
            
package() {
  install -Dm644 "${srcdir}/license.pdf" "${pkgdir}/usr/share/licenses/${pkgname}/license.pdf"
  install -Dm644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
  install -Dm755 "${srcdir}/${pkgname%-standalone}" "${pkgdir}/usr/bin/${pkgname%-standalone}"
}
