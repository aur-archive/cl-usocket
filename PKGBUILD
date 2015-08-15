# Maintainer: kristof <soderstroff@gmail.com>

pkgname=cl-usocket
_clname=usocket
pkgver=0.6.1
pkgrel=2
pkgdesc="Portable TCP/IP interface for Common Lisp"
arch=('any')
#options=('docs') TODO
url="http://common-lisp.net/project/usocket/"
license=('MIT')
depends=('common-lisp' 'cl-utilities')
install=cl-usocket.install
source=("http://common-lisp.net/project/usocket/releases/usocket-$pkgver.tar.gz")
md5sums=('4cb34bdf3bbeff5732098e9446a6d04b')

package() {
    install -d ${pkgdir}/usr/share/common-lisp/source/${_clname}
    install -d ${pkgdir}/usr/share/common-lisp/source/${_clname}/backend
    install -d ${pkgdir}/usr/share/common-lisp/source/${_clname}/vendor
    install -d ${pkgdir}/usr/share/common-lisp/systems
    install -d ${pkgdir}/usr/share/doc/${pkgname}
    install -d ${pkgdir}/usr/share/licenses/${pkgname}

    cd ${srcdir}/${_clname}-${pkgver}

    # usocket
    install -m 644 -t ${pkgdir}/usr/share/common-lisp/source/${_clname} \
        ${srcdir}/${_clname}-${pkgver}/*.lisp
    install -m 644 -t ${pkgdir}/usr/share/common-lisp/source/${_clname} \
        ${srcdir}/${_clname}-${pkgver}/*.asd
    # backends' files (cl implementations)
    install -m 644 -t ${pkgdir}/usr/share/common-lisp/source/${_clname}/backend \
        ${srcdir}/${_clname}-${pkgver}/backend/*.lisp
    # vendor
    install -m 644 -t ${pkgdir}/usr/share/common-lisp/source/${_clname}/vendor \
        ${srcdir}/${_clname}-${pkgver}/vendor/*.lisp
    # docs
    install -m 644 -t ${pkgdir}/usr/share/doc/${pkgname} \
        ${srcdir}/${_clname}-${pkgver}/doc/*.txt
    # license
    install -m 644 ${srcdir}/${_clname}-${pkgver}/LICENSE \
        ${pkgdir}/usr/share/licenses/${pkgname}/
    # system file
    cd ${pkgdir}/usr/share/common-lisp/systems
    ln -s ../source/${_clname}/${_clname}.asd .
}

# vim:set ts=2 sw=4 et nospell:
