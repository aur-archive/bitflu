# Maintainer:  TDY <tdy@gmx.com>
# Contributor: stalker254 <stalker254@gmail.com>

pkgname=bitflu
pkgver=1.50
pkgrel=1
pkgdesc="A download daemon supporting the BitTorrent and HTTP protocols"
arch=('any')
url="http://bitflu.workaround.ch/"
license=('PerlArtistic')
depends=('perl-danga-socket' 'perl-digest-sha1')
source=(http://$pkgname.workaround.ch/$pkgname/$pkgname-$pkgver.tgz)
md5sums=('30857e784ff6ffd77fe4795426562cee')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  sed -i "s,\.\(/plugins\),/usr/share/$pkgname\1," $pkgname.pl
  install -Dm755 $pkgname.pl "$pkgdir/usr/bin/$pkgname"
  install -Dm644 README.txt "$pkgdir/usr/share/doc/$pkgname/README"
  install -m644 README_IPv6.txt "$pkgdir/usr/share/doc/$pkgname/"

  install -dm755 "$pkgdir/usr/share/$pkgname/plugins/Bitflu"
  install -m644 plugins/Bitflu/*.pm "$pkgdir/usr/share/$pkgname/plugins/Bitflu"
  install -m644 $pkgname.config.example "$pkgdir/usr/share/$pkgname"
}

