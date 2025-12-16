# Maintainer: Morgan <morganamilo@archlinux.org>
pkgname=paru-bin
pkgver=2.1.0
pkgrel=1
pkgdesc='Feature packed AUR helper'
url='https://github.com/morganamilo/paru'
source=("https://github.com/Morganamilo/paru/releases/download/v2.1.0/paru-v2.1.0-$CARCH.tar.zst")
backup=("etc/paru.conf")
arch=('x86_64' 'armv7h' 'aarch64')
license=('GPL-3.0-or-later')
depends=('git' 'pacman' 'libalpm.so>=14')
optdepends=('bat: colored pkgbuild printing' 'devtools: build in chroot and downloading pkgbuilds')
conflicts=('paru' 'paru-debug')
sha256sums=('28ef88736080e7e96e569f7adf10517ef8310a68b528e7f34c795287d7271880')

package() {
  cd "$srcdir"

  install -Dm755 paru "${pkgdir}/usr/bin/paru"
  install -Dm644 paru.conf "${pkgdir}/etc/paru.conf"

  install -Dm644 man/paru.8 "$pkgdir/usr/share/man/man8/paru.8"
  install -Dm644 man/paru.conf.5 "$pkgdir/usr/share/man/man5/paru.conf.5"

  install -Dm644 completions/bash "${pkgdir}/usr/share/bash-completion/completions/paru.bash"
  install -Dm644 completions/fish "${pkgdir}/usr/share/fish/vendor_completions.d/paru.fish"
  install -Dm644 completions/zsh "${pkgdir}/usr/share/zsh/site-functions/_paru"

  install -d "$pkgdir/usr/share/"
  cp -r locale "$pkgdir/usr/share/"
}
