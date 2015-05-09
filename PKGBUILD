# Maintainer: 
# Contributor: xantares

pkgbase=python-snowballstemmer
pkgname=('python-snowballstemmer' 'python2-snowballstemmer')
pkgver=1.2.0
pkgrel=1
arch=(any)
pkgdesc="Snowball stemming library collection for Python"
url='https://github.com/shibukawa/snowball_py'
license=(BSD)
makedepends=(python-setuptools python2-setuptools)
source=("https://pypi.python.org/packages/source/s/snowballstemmer/snowballstemmer-${pkgver}.tar.gz" 'LICENSE')
md5sums=('51f2ef829db8129dd0f2354f0b209970'
         'e269a6e5398d3795d4077cef3152aa33')

build() {
  cp -r ${srcdir}/snowballstemmer-${pkgver} ${srcdir}/snowballstemmer-${pkgver}-py2
  
  cd "$srcdir"/snowballstemmer-${pkgver}
  python setup.py build

  cd "$srcdir"/snowballstemmer-${pkgver}-py2
  python2 setup.py build
}

package_python-snowballstemmer() {
  cd "$srcdir"/snowballstemmer-${pkgver}
  python setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 "$srcdir"/LICENSE "$pkgdir"/usr/share/licenses/python-snowballstemmer/LICENSE
}

package_python2-snowballstemmer() {
  cd "$srcdir"/snowballstemmer-${pkgver}-py2 
  python2 setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 "$srcdir"/LICENSE "$pkgdir"/usr/share/licenses/python2-snowballstemmer/LICENSE
}
