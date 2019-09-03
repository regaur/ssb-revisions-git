# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname=ssb-revisions-git
pkgver=1.4.1.r86.f0c394f
pkgrel=1
pkgdesc="Mutable documents for secure scuttlebutt"
arch=('any')
url=""
license=('GPL')
groups=()
depends=('scuttlebot')
makedepends=('git' 'npm')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()

source=("git+ssh://git@github.com/regular/${pkgname%-git}.git")

sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
  printf "%s.r%s.%s" "$(node -e 'console.log(require("./package.json").version)')" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package () {
	cd "$srcdir/${pkgname%-git}"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" regular/${pkgname%-git}
}
