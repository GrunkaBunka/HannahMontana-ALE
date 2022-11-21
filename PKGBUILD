# Maintainer: Yuvraj Mishra <yuvrajmishrawork@gmail.com>

pkgname=python2-bin
_pkgname=python2
pkgver=2.7.18_1
_pybasever=2.7
pkgrel=1
pkgdesc="Python2 binaries for x86_64"
arch=('x86_64')
url="https://python.org"
license=('PSF')
groups=()
depends=('bzip2' 'expat' 'gdbm' 'libffi' 'libnsl' 'libxcrypt' 'openssl' 'sqlite' 'zlib')
makedepends=()
checkdepends=()
optdepends=()
provides=('python2')
conflicts=('python2')
replaces=()
backup=()
options=()
install=
changelog=
noextract=()
validpgpkeys=()
source=("https://github.com/VanillaBase1lb/python2-bin-aur/releases/download/$pkgver/python2-build.tar.gz")
md5sums=('d1a5929835018fa5ca18853c49c972ad')


package() {
	# cd python2-build

	# find -type l -delete
	rm python2-build/bin/2to3
	rm python2-build/bin/idle
	rm python2-build/bin/pydoc
	rm python2-build/bin/python
	rm python2-build/bin/python-config

	sed -i "s|/mnt/storage/temp/python2-build|/usr|" python2-build/bin/python${_pybasever}-config
	sed -i "s|/mnt/storage/temp/python2-build|/usr|" python2-build/lib/pkgconfig/python-${_pybasever}.pc

	# copy recursively without overwriting
	mkdir -p $pkgdir/usr
	cp -rn python2-build/* "${pkgdir}/usr/" || true
	# install -DCm755 bin/python2* -t "${pkgdir}/usr/bin" || echo ""
	# install -DCm755 include/python${_pybasever}/* -t "${pkgdir}/usr/include/python${_pybasever}" || echo ""
	# install -DCm755 lib/* -t "${pkgdir}/usr/lib" || echo ""
	# install -DCm755 lib/pkgconfig/* -t "${pkgdir}/usr/lib/pkgconfig" || echo ""
	# install -DCm755 lib/python${_pybasever}/* -t "${pkgdir}/usr/lib/python${_pybasever}" || echo ""
	# install -DCm755 share/man/man1/* -t "${pkgdir}/usr/share/man/man1" || echo ""

	# ln "${pkgdir}"/usr/bin/python${_pybasever}        "${pkgdir}"/usr/bin/python2
	# ln "${pkgdir}"/usr/bin/python${_pybasever}-config "${pkgdir}"/usr/bin/python2-config
	# ln "${pkgdir}"/usr/lib/pkgconfig/python-${_pybasever}.pc "${pkgdir}"/usr/lib/pkgconfig/python2.pc
	# ln "${pkgdir}"/usr/lib/libpython${_pybasever}.so.1.0 "${pkgdir}"/usr/lib/libpython2.so.1.0
	# ln "${pkgdir}"/usr/share/man/man1/python${_pybasever}.1      "${pkgdir}"/usr/share/man/man1/python2.1
	# fix conflicts with python
	#mv "${pkgdir}"/usr/bin/idle{,2}
	#mv "${pkgdir}"/usr/bin/pydoc{,2}
	#mv "${pkgdir}"/usr/bin/2to3{,-2.7}
}
