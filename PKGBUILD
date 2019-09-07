# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: xantares

pkgbase=python-snowballstemmer
pkgname=('python-snowballstemmer' 'python2-snowballstemmer')
pkgver=1.9.1
pkgrel=1
arch=('any')
pkgdesc="Snowball stemming library collection for Python"
url='https://github.com/shibukawa/snowball_py'
license=('BSD')
makedepends=('python' 'python2')
source=("https://pypi.python.org/packages/source/s/snowballstemmer/snowballstemmer-$pkgver.tar.gz")
md5sums=('00324762f8a0e6889353926e2c9767fb')

prepare() {
  cp -a snowballstemmer-$pkgver{,-py2}
}

build() {
  cd "$srcdir"/snowballstemmer-$pkgver
  python setup.py build

  cd "$srcdir"/snowballstemmer-$pkgver-py2
  python2 setup.py build
}

check() {
  cd "$srcdir"/snowballstemmer-$pkgver/src
  PYTHONPATH=. python sample/testapp.py english "what's this"

  cd "$srcdir"/snowballstemmer-$pkgver-py2/src
  PYTHONPATH=. python2 sample/testapp.py english "what's this"
}

package_python-snowballstemmer() {
  depends=('python')
  optdepends=('python-pystemmer: for improved performance')

  cd "$srcdir"/snowballstemmer-$pkgver
  python setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
}

package_python2-snowballstemmer() {
  depends=('python2')
  optdepends=('python2-pystemmer: for improved performance')

  cd "$srcdir"/snowballstemmer-$pkgver-py2 
  python2 setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 COPYING "$pkgdir"/usr/share/licenses/$pkgname/COPYING
}
