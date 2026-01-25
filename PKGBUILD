# Maintainer: itzTweak <itzTweak@pm.me>
pkgname=waydroid-panthor-config
pkgver=240416
pkgrel=1
pkgdesc="Waydroid configuration and services for Panthor GPU (FydeTab Duo)"
arch=('aarch64')
url="https://github.com/tweakz-fydetab-hacks/tweakz-fydetab-hacks"
license=('MIT')
depends=('waydroid' 'waydroid-panthor-images')
install=${pkgname}.install

source=("dev-binderfs.mount"
        "waydroid-binder-setup.service"
        "waydroid-panthor-init"
        "waydroid-panthor-init.service"
        "waydroid-test"
        "waydroid-test.desktop"
        "waydroid.conf")
sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP')

package() {
    # Create directories
    install -dm755 "${pkgdir}/usr/lib/systemd/system"
    install -dm755 "${pkgdir}/usr/lib/modules-load.d"
    install -dm755 "${pkgdir}/usr/local/bin"
    install -dm755 "${pkgdir}/usr/share/applications"

    # Install systemd units
    install -Dm644 "${srcdir}/dev-binderfs.mount" "${pkgdir}/usr/lib/systemd/system/dev-binderfs.mount"
    install -Dm644 "${srcdir}/waydroid-binder-setup.service" "${pkgdir}/usr/lib/systemd/system/waydroid-binder-setup.service"
    install -Dm644 "${srcdir}/waydroid-panthor-init.service" "${pkgdir}/usr/lib/systemd/system/waydroid-panthor-init.service"

    # Install modules-load.d config to load binder module at boot
    install -Dm644 "${srcdir}/waydroid.conf" "${pkgdir}/usr/lib/modules-load.d/waydroid.conf"

    # Install scripts
    install -Dm755 "${srcdir}/waydroid-panthor-init" "${pkgdir}/usr/local/bin/waydroid-panthor-init"
    install -Dm755 "${srcdir}/waydroid-test" "${pkgdir}/usr/local/bin/waydroid-test"

    # Install desktop file
    install -Dm644 "${srcdir}/waydroid-test.desktop" "${pkgdir}/usr/share/applications/waydroid-test.desktop"
}
