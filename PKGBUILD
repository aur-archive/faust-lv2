## Maintainer: rtfreedman (rob<d0t>til<d0t>freedman<aT>gmail<d0t>com
## Contributor: SpepS <dreamspepser at yahoo dot it>
pkgname=faust-lv2
pkgver=0.5
pkgrel=2
pkgdesc="An LV2 architecture for the Faust programming language"
arch=(i686 x86_64)
url="https://bitbucket.org/agraef/faust-lv2/"
license=('GPL3' 'LGPL3')
depends=('faust' 'lv2')
source=("https://bitbucket.org/agraef/faust-lv2/downloads/faust-lv2-$pkgver.tar.bz2")
md5sums=('4e482ed468c960e953e4aa1793987aa6')

build() {
  cd "$pkgname-$pkgver"
  # use files installed by Faust 0.9.67
  rm lv2.cpp lv2synth.cpp 
  ln -s /usr/lib/faust/lv2.cpp lv2.cpp
  ln -s /usr/lib/faust/lv2synth.cpp lv2synth.cpp
  
  make split-bundle
}

package() {
  cd "$pkgname-$pkgver"
  make install-split  prefix=/usr DESTDIR="$pkgdir"
}
