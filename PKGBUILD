# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
_gemname=wasabi
pkgname=ruby-$_gemname-2.5
pkgver=2.5.1
pkgrel=2
pkgdesc='A simple WSDL parser for Ruby'
arch=(any)
url='https://github.com/savonrb/wasabi'
license=('MIT')
depends=('ruby' 'ruby-httpi-1.1' 'ruby-nokogiri>=1.4.0')
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$_gemname-$pkgver.gem"
}
md5sums=('f6534044d9bf0fe76d956acf00453cac')
