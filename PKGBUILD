# Contributor: Olivier Mehani <olivier.mehani@nicta.com.au>
pkgname=oml2-apps
_redmineid=1142
_srcver=2.11.0
pkgver=2.11.0
pkgrel=1
pkgdesc="OML2 applications collection"
arch=(i686 x86_64)
url="http://omlapp.mytestbed.net/"
license=('custom:MIT-Nicta')
depends=('oml2')
optdepends=(
'collectd: for the write_oml plugin'
'gpsd: for gpslogger'
'libsigar: for nmetrics'
'libtrace: for trace'
'wpa_supplicant: for wpamon')
makedepends=('git')
install='oml2-apps.install'
source=(
	http://oml.mytestbed.net/attachments/download/${_redmineid}/oml2-apps-${_srcver}.tar.gz
)

_builddir=${pkgname}-${_srcver}

build() {
	cd "${srcdir}"
	cd "${srcdir}/${_builddir}"
	./configure --prefix=/usr
	make || return 1
}

package() {
	cd "${srcdir}/${_builddir}"
	make DESTDIR="${pkgdir}/" install
}
md5sums=('cf45ccad8b558b540d5a84735f2cb243')
