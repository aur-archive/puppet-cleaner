# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
pkgname=puppet-cleaner
pkgver=0.3.1
pkgrel=2
pkgdesc='Transforms Puppet DSL source code to make it comply with the style guide'
arch=(any)
url='https://github.com/santana/puppet-cleaner/'
license=('BSD')
depends=('puppet')
noextract=($pkgname-$pkgver.gem)
source=(https://rubygems.org/downloads/$pkgname-$pkgver.gem)

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$pkgname-$pkgver.gem"
}
md5sums=('03a06eb22de19697abf138ac569c6559')
