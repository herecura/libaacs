# $Id: PKGBUILD 219787 2017-03-29 09:23:47Z jelle $
# Maintainer:  Martin Wimpress <code@flexion.org>
# Contributor: Gustavo Alvarez <sl1pkn07@gmail.com>
# Contributor: Dirk Berg <berg1981@googlemail.com>

pkgname=libaacs
pkgver=0.9.0
pkgrel=1
pkgdesc="Advanced Access Content System"
arch=('i686' 'x86_64')
license=('LGPL')
url="http://www.videolan.org/developers/libaacs.html"
depends=('libgcrypt')
source=("ftp://ftp.videolan.org/pub/videolan/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.bz2")
sha1sums=('b658830b760e756a46486cc4ab47dacef31994ab')

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./bootstrap
    ./configure --prefix=/usr
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    install -Dm644 KEYDB.cfg "${pkgdir}/usr/share/doc/${pkgname}"/KEYDB.cfg
    install -Dm644 README.txt "${pkgdir}/usr/share/doc/${pkgname}"/README.txt
}