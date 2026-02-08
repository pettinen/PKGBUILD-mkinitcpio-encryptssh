pkgname=mkinitcpio-encryptssh
pkgver=1.0.0
pkgrel=1
pkgdesc='Hook to enable disk decryption over SSH in early userspace'
arch=(any)
license=(BSD-3-Clause)
depends=(cryptsetup dropbear iproute2 mkinitcpio-nfs-utils psmisc)
source=("mkinitcpio-dropbear-$pkgver.tar.gz::https://github.com/pettinen/mkinitcpio-dropbear/archive/refs/tags/v$pkgver.tar.gz"
        "mkinitcpio-netconf-$pkgver.tar.gz::https://github.com/pettinen/mkinitcpio-netconf/archive/refs/tags/v$pkgver.tar.gz"
        "mkinitcpio-utils-$pkgver.tar.gz::https://github.com/pettinen/mkinitcpio-utils/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('5be094d3f82dd3c99a4c39b21b000a3a7adf445308581606e29f87c331afe13a'
            '56e7219fb7dfe2708f85e3f4ebc71a094632b7ddc4d501b382f63768027e3864'
            '7a688c66e5b342f480fda40837852e62aebe12f0480a00bfc7ee450e7ed9f45a')

function package {
    install -Dm0644 "mkinitcpio-dropbear-$pkgver/dropbear_hook" "$pkgdir/usr/lib/initcpio/hooks/dropbear"
    install -Dm0644 "mkinitcpio-dropbear-$pkgver/dropbear_install" "$pkgdir/usr/lib/initcpio/install/dropbear"
    install -Dm0644 "mkinitcpio-netconf-$pkgver/netconf_hook" "$pkgdir/usr/lib/initcpio/hooks/netconf"
    install -Dm0644 "mkinitcpio-netconf-$pkgver/netconf_install" "$pkgdir/usr/lib/initcpio/install/netconf"
    install -Dm0644 "mkinitcpio-utils-$pkgver/initcpio/hooks/encryptssh" "$pkgdir/usr/lib/initcpio/hooks/encryptssh"
    install -Dm0644 "mkinitcpio-utils-$pkgver/initcpio/install/encryptssh" "$pkgdir/usr/lib/initcpio/install/encryptssh"
    install -Dm0755 "mkinitcpio-utils-$pkgver/utils/shells/cryptsetup_shell" "$pkgdir/usr/share/$pkgname/cryptsetup_shell"
}
