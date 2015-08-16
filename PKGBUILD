#Maintainer:Kwrazi<kwrazi@gmail.com>

# Bug: can't use comma in pkgname
pkgname="i-librarian"
pkgver=3.1
pkgrel=2
pkgdesc="Academic software for managing research papers (web client)"
arch=('any')
url="http://i-librarian.net/"
license=('GPL3')
depends=('php-apache' 
         'php-sqlite' 
         'php-gd' 'poppler' 
         'bibutils' 
         'ghostscript' 
         'pdftk')
backup=("etc/webapps/${pkgname}/.htaccess")
install=${pkgname}.install
source=("http://i-librarian.net/downloads/I,-Librarian-3.1-Linux.tar.xz" 
        "apache.example.conf")
md5sums=('93d00bce8dcf9c9d72719e5a77f8c9cb'
         'bd0d90bf4210dcf522a0d0820b91e26c')

package() {
    _instdir=/usr/share/webapps/${pkgname}
    _etcdir=/etc/webapps/${pkgname}
    	
    mkdir -p ${pkgdir}/${_instdir} ${pkgdir}/${_etcdir}
    	
    cd ${pkgdir}/${_instdir}
    cp -ra ${srcdir}/* .
    mv library/.htaccess ${pkgdir}/${_etcdir}
    ln -s /etc/webapps/${pkgname}/.htaccess library/.htaccess
	
    install -Dm644 ${srcdir}/apache.example.conf ${pkgdir}/${_etcdir}/apache.example.conf

    rm ${pkgdir}/${_instdir}/$(basename ${source[0]})
    rm ${pkgdir}/${_instdir}/$(basename ${source[1]})
}
