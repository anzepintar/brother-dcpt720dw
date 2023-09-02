# Maintainer: Anže Pintar <anze <at> anzepintar <dot> com>
# Based on https://aur.archlinux.org/packages/brother-dcpt525w by Nickolay

pkgname=brother-dcpt720dw
pkgver=3.5.0
pkgrel=1
pkgdesc="Brother printer driver (lpd/cups) for the DCP-T720DW multifuncional printer"
url="https://support.brother.com/g/b/producttop.aspx?c=eu_ot&lang=en&prod=dcpt720dw_all"
license=('custom: Brother License' 'EULA' 'GPL')
arch=('i686' 'x86_64')
optdepends=('sane: scanning support'
            'sane-airscan: SANE backend for AirScan (eSCL) and WSD document scanners'
            'brscan5: making dcpt720dw scaner available to sane'
            'brscan-skey: scankey support if connected via usb')

depends=('a2ps' 'cups')
depends_x86_64=('lib32-glibc')
install="dcpt720dw.install"

source=(
  "https://download.brother.com/welcome/dlf105179/dcpt720dwpdrv-$pkgver-$pkgrel.i386.deb" \
  "spool.patch"
)
sha256sums=(
  'SKIP' \
  'SKIP'
)

package() {
  install_scripts="/opt/brother/Printers/dcpt720dw/scripts"
  scripts="${pkgdir}${install_scripts}"
  mkdir -p "${scripts}"
  tar -xf control.tar.gz -C "${scripts}"
  tar -xf data.tar.gz -C "${pkgdir}"
  cd "${pkgdir}"
  patch -Np0 < "${srcdir}/spool.patch"
}
