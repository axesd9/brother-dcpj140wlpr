# Maintainer: Chanathip Srithanrat <axesd9@gmail.com>

pkgname=brother-dcpj140wlpr
pkgver=1.1.3_6
pkgrel=1
pkgdesc='Brother DCP-J140W LPR printer driver'
arch=('x86_64')
url='http://support.brother.com/g/s/id/linux/en/'
license=('custom:brother')
depends=('lib32-glibc')
install="$pkgname.install"
source=("http://download.brother.com/welcome/dlf101743/${pkgname#brother-}-${pkgver/_/-}.i386.deb"
        "http://support.brother.com/g/s/agreement/English_lpr/agree.html"
        "lp.patch")
md5sums=('74f82abbecd1e09f5c152d9a21e99905'
         '5a4a3172f6278922062aa6e1f43b0d92'
         'f560ac8da495a4a8b45b5e9226128cf5')

prepare() {
    bsdtar xf data.tar.gz
    patch -p0 < lp.patch
}

package() {
    cp -R opt $pkgdir
    install -d $pkgdir/var/spool/lpd
    install -Dm755 usr/bin/brprintconf_dcpj140w $pkgdir/usr/bin/brprintconf_dcpj140w
    install -Dm644 agree.html $pkgdir/usr/share/licenses/$pkgname/LICENSE.html
}
