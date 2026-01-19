# Maintainer: Daniel M. Capella <polyzen@archlinux.org>
# Contributor: Carlo Teubner <carlo@cteubner.net>

pkgname=wtype
pkgver=0.4.git~de26c46
pkgrel=1
pkgdesc='xdotool type for wayland'
arch=('x86_64')
url=https://github.com/atx/wtype
license=('MIT')
depends=('libxkbcommon' 'wayland')
makedepends=('git' 'meson')
source=("git+https://github.com/mattbnz/wtype.git#branch=claude/fix-wtype-chromium-2F7bD")
sha256sums=('SKIP')

pkgver() {
  cd wtype
  printf "0.4.git~%s" "$(git rev-parse --short HEAD)"
}

build() {
  cd wtype
  arch-meson build
  ninja -C build
}

package() {
  cd wtype
  DESTDIR="$pkgdir" ninja -C build install
  install -Dm644 -t "$pkgdir"/usr/share/licenses/$pkgname LICENSE
}

# vim:set ts=2 sw=2 et:
