# Maintainer: Felix E. xelif@icqmail.com

# Upstream name of extension:
_extname=ExternalLinks
# Variant valid as package name:
_extpkgname=externallinks

pkgname=mediawiki-ext-$_extpkgname-git
pkgver=v1.23.r0.gb30200f
pkgrel=2
pkgdesc="A MediaWiki extension for listing and validating external links"
source=("$_extname::git+https://github.com/roman-1983/mediawiki-ExternalLinks")
md5sums=("SKIP")
arch=("any")
url="http://http://www.mediawiki.org/wiki/Extension:$_extname"
license=("GPL")
depends=("mediawiki")
makedepends=("git")
provides=("mediawiki-ext-$_extpkgname")
conflicts=()

pkgver() {
  cd $_extname
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

package() {
  # Target extension directory of MediaWiki:
  _extdir="$pkgdir/usr/share/webapps/mediawiki/extensions"
  mkdir -p "$_extdir"
  rsync -a $_extname "$_extdir/" --exclude .git
}