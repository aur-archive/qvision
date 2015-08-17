# Contributer: giacomogiorgianni@gmail.com 

pkgname=qvision
pkgver=0.8.1
pkgrel=3
pkgdesc="Object oriented multi-platform library for computer vision, image processing and augmented reality based on Qt."
url="https://opendesktop.org/content/show.php/QVision?content=132363"
arch=('i686' 'x86_64')
license=('LGPL')
depends=('qt4')
source=("http://switch.dl.sourceforge.net/project/qvision/QVision%200.8.1/$pkgname.$pkgver.zip")
md5sums=('b8f1dc32538da3b11d7d49cf8bc28504')

package() {
  cd "$srcdir/${pkgname}.${pkgver}"
  mv config.pri.example config.pri
  qmake-qt4 $pkgname.pro -r -config release \
    "CONFIG+=LINUX_INTEGRATED" \
    "INSTALL_PATH=$pkgdir/usr/" \
    "LOWERED_APPNAME=$pkgname"
  make all
  make INSTALL_PATH=${pkgdir} install
 rm -rf ${pkgdir}/usr/src
 install -dm755 "${pkgdir}/usr/share/doc/$pkgname"
 cp -pR  doc/* ${pkgdir}/usr/share/doc/$pkgname
 cp -pR  examples ${pkgdir}/usr/share/doc/$pkgname
 mv ${pkgdir}/usr/{COPYING,COPYING.LESSER,README,common.pri,config.pri,qvproject.pri} ${pkgdir}/usr/share/doc/$pkgname
}