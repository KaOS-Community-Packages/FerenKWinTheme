pkgname=FerenKWinTheme
_gitname=FerenKWinTheme
pkgver=r19.1ec2c15
pkgrel=1
pkgdesc="A fork of KDE Breeze decoration with additional options"
arch=('x86_64')
url="https://github.com/feren-OS/FerenKWinTheme"
license=('GPL3.0')
depends=('kwin')
makedepends=('git' 'cmake' 'extra-cmake-modules')
source=("git+${url}.git")
sha256sums=('SKIP')

pkgver() {
  
   cd ${srcdir}/${_gitname}

   printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  
}

build() {

   cd ${srcdir}/${_gitname}
  
   mkdir build && cd build
   cmake ..  \
            -DCMAKE_INSTALL_PREFIX=/usr \
            -DCMAKE_BUILD_TYPE=Release \
            -DKDE_INSTALL_LIBDIR=lib \
            -DBUILD_TESTING=OFF \
            -DKDE_INSTALL_USE_QT_SYS_PATHS=ON

}

package() {
    
   make -C ${srcdir}/${_gitname}/build DESTDIR="$pkgdir" install        

}
