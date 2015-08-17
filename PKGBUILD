
pkgname=('uwsgi-stable-python2')
_pkgbase=uwsgi
pkgver=1.9.12
pkgrel=1
epoch=
pkgdesc="uWSGI is a fast, self-healing and developer/sysadmin-friendly application container server coded in pure C. Splitted package to support python, python2, ruby (rack), ... "
arch=(i686 x86_64 arm armv6h)
url="http://projects.unbit.it/uwsgi/"
license=('GPL2')
groups=()
depends=('libyaml' 'jansson' 'uwsgi-stable-core' 'python2')
makedepends=('python2')
checkdepends=()
provides=('uwsgi-python2')
conflicts=('uwsgi-python2')
replaces=('uwsgi')
backup=()
options=()
install=
changelog=
source=("http://projects.unbit.it/downloads/$_pkgbase-$pkgver.tar.gz")
noextract=()
md5sums=('93e561fcd4d7da48aafaf2a85095df58')


build() {
  cd "$srcdir/$_pkgbase-$pkgver"
  python2 uwsgiconfig.py --plugin plugins/python core python27
  python2 uwsgiconfig.py --plugin plugins/gevent core gevent

}

package() {

  cd "$srcdir/$_pkgbase-$pkgver"
  mkdir -p "$pkgdir/usr/lib/uwsgi/"
  mkdir -p "$pkgdir/usr/bin/"
  install -Dm555 python27_plugin.so "$pkgdir/usr/lib/uwsgi"
  install -Dm555 gevent_plugin.so "$pkgdir/usr/lib/uwsgi"
  ln -s "/usr/bin/uwsgi" "$pkgdir/usr/bin/uwsgi_python27"
}
